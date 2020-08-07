---
title: Uzyskiwanie szacunkowych poziomów energii
description: Zapoznaj się z przykładowym Q# programem, który szacuje wartości poziomu energii wodoru.
author: guanghaolow
ms.author: gulow
ms.date: 07/02/2020
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.energyestimate
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2df4b829a3f4946c6de6e6b80ad72a5bc192b2c
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869209"
---
# <a name="obtaining-energy-level-estimates"></a><span data-ttu-id="103b7-103">Uzyskiwanie szacunkowych poziomów energii</span><span class="sxs-lookup"><span data-stu-id="103b7-103">Obtaining energy level estimates</span></span>
<span data-ttu-id="103b7-104">Oszacowanie wartości poziomów energii jest jednym z głównych zastosowań chemii Quantum.</span><span class="sxs-lookup"><span data-stu-id="103b7-104">Estimating the values of energy levels is one of the principal applications of quantum chemistry.</span></span> <span data-ttu-id="103b7-105">W tym artykule opisano, jak można wykonać to dla kanonicznego przykładu wodoru.</span><span class="sxs-lookup"><span data-stu-id="103b7-105">This article outlines how you can perform this for the canonical example of molecular hydrogen.</span></span> <span data-ttu-id="103b7-106">Przykład przywoływany w tej sekcji znajduje się [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) w repozytorium próbek chemii.</span><span class="sxs-lookup"><span data-stu-id="103b7-106">The sample referenced in this section is [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) in the chemistry samples repository.</span></span> <span data-ttu-id="103b7-107">Jest to przykładowy przykład wizualizacji, który przedstawia dane wyjściowe [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) .</span><span class="sxs-lookup"><span data-stu-id="103b7-107">A more visual example that plots the output is the [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogenGUI) demo.</span></span>

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a><span data-ttu-id="103b7-108">Oszacowanie wartości energetycznych wodoru</span><span class="sxs-lookup"><span data-stu-id="103b7-108">Estimating the energy values of molecular hydrogen</span></span>

<span data-ttu-id="103b7-109">Pierwszym krokiem jest utworzenie hamiltonian reprezentującego wodór molekularny.</span><span class="sxs-lookup"><span data-stu-id="103b7-109">The first step is to construct the Hamiltonian representing molecular hydrogen.</span></span> <span data-ttu-id="103b7-110">Chociaż można utworzyć ten program przy użyciu narzędzia NWChem, w przypadku zwięzłości, ten przykład ręcznie dodaje warunki hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="103b7-110">Although you can construct this using the NWChem tool, for brevity, this sample adds the Hamiltonian terms manually.</span></span>

```csharp
    // These orbital integrals are represented using the OrbitalIntegral
    // data structure.
    var energyOffset = 0.713776188; // This is the coulomb repulsion
    var nElectrons = 2; // Molecular hydrogen has two electrons
    var orbitalIntegrals = new OrbitalIntegral[]
    {
        new OrbitalIntegral(new[] { 0,0 }, -1.252477495),
        new OrbitalIntegral(new[] { 1,1 }, -0.475934275),
        new OrbitalIntegral(new[] { 0,0,0,0 }, 0.674493166),
        new OrbitalIntegral(new[] { 0,1,0,1 }, 0.181287518),
        new OrbitalIntegral(new[] { 0,1,1,0 }, 0.663472101),
        new OrbitalIntegral(new[] { 1,1,1,1 }, 0.697398010),
        // This line adds the identity term.
        new OrbitalIntegral(new int[] { }, energyOffset)
    };

    // Initialize a fermion Hamiltonian data structure and add terms to it.
    var fermionHamiltonian = new OrbitalIntegralHamiltonian(orbitalIntegrals).ToFermionHamiltonian();
```

<span data-ttu-id="103b7-111">Symulowanie hamiltonian wymaga przekonwertowania operatorów Fermion na operatory qubit.</span><span class="sxs-lookup"><span data-stu-id="103b7-111">Simulating the Hamiltonian requires converting the fermion operators to qubit operators.</span></span> <span data-ttu-id="103b7-112">Ta konwersja jest wykonywana za pomocą kodowania Jordania-Wigner w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="103b7-112">This conversion is performed through the Jordan-Wigner encoding as follows:</span></span>

```csharp
    // The Jordan-Wigner encoding converts the fermion Hamiltonian, 
    // expressed in terms of fermionic operators, to a qubit Hamiltonian,
    // expressed in terms of Pauli matrices. This is an essential step
    // for simulating our constructed Hamiltonians on a qubit quantum
    // computer.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);

    // You also need to create an input quantum state to this Hamiltonian.
    // Use the Hartree-Fock state.
    var fermionWavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons);

    // This Jordan-Wigner data structure also contains a representation 
    // of the Hamiltonian and wavefunction made for consumption by the Q# operations.
    var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
    var qSharpWavefunctionData = fermionWavefunction.ToQSharpFormat();
    var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

<span data-ttu-id="103b7-113">Następnie Przekaż `qSharpData` , który reprezentuje hamiltonian, do `TrotterStepOracle` funkcji.</span><span class="sxs-lookup"><span data-stu-id="103b7-113">Next, pass `qSharpData`, which represents the Hamiltonian, to the `TrotterStepOracle` function.</span></span> <span data-ttu-id="103b7-114">`TrotterStepOracle`zwraca operację Quantum, która przybliży ewolucję hamiltonian w czasie rzeczywistym.</span><span class="sxs-lookup"><span data-stu-id="103b7-114">`TrotterStepOracle` returns a quantum operation that approximates the real-time evolution of the Hamiltonian.</span></span> <span data-ttu-id="103b7-115">Aby uzyskać więcej informacji, zobacz [symulowanie hamiltonian Dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span><span class="sxs-lookup"><span data-stu-id="103b7-115">For more information, see [Simulating Hamiltonian dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);
```

<span data-ttu-id="103b7-116">W tym momencie można użyć [algorytmów szacowania fazy](xref:microsoft.quantum.libraries.characterization) standardowej biblioteki, aby poznać energię stanu ziemi przy użyciu poprzedniej symulacji.</span><span class="sxs-lookup"><span data-stu-id="103b7-116">At this point, you can use the standard library's [phase estimation algorithms](xref:microsoft.quantum.libraries.characterization) to learn the ground state energy using the previous simulation.</span></span> <span data-ttu-id="103b7-117">Wymaga to przygotowania dobrego zbliżania do stanu ziemi Quantum.</span><span class="sxs-lookup"><span data-stu-id="103b7-117">This requires preparing a good approximation to the quantum ground state.</span></span> <span data-ttu-id="103b7-118">Sugestie dotyczące tych przybliżeń znajdują się w [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schemacie.</span><span class="sxs-lookup"><span data-stu-id="103b7-118">Suggestions for such approximations are provided in the [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schema.</span></span> <span data-ttu-id="103b7-119">Niemniej jednak te sugestie, domyślne podejście dodaje wiele Electrons, `hamiltonian.NElectrons` Aby greedily zminimalizować okresy świetlne jednego z nich.</span><span class="sxs-lookup"><span data-stu-id="103b7-119">However, absent these suggestions, the default approach adds a number of `hamiltonian.NElectrons` electrons to greedily minimize the diagonal one-electron term energies.</span></span> <span data-ttu-id="103b7-120">Funkcje i operacje szacowania fazy są dostępne w notacji DocFX w przestrzeni nazw [Microsoft. Quantum. charakteryzującą](xref:microsoft.quantum.characterization) .</span><span class="sxs-lookup"><span data-stu-id="103b7-120">The phase estimation functions and operations are provided in DocFX notation in the [Microsoft.Quantum.Characterization](xref:microsoft.quantum.characterization) namespace.</span></span>

<span data-ttu-id="103b7-121">Poniższy fragment kodu przedstawia sposób, w jaki dane wyjściowe ewolucji w czasie rzeczywistym przez bibliotekę symulacji chemicznej integrują się z oszacowaniem fazy Quantum.</span><span class="sxs-lookup"><span data-stu-id="103b7-121">The following snippet shows how the real-time evolution output by the chemistry simulation library integrates with quantum phase estimation.</span></span>

```qsharp
operation GetEnergyByTrotterization (
    qSharpData : JordanWignerEncodingData, 
    nBitsPrecision : Int, 
    trotterStepSize : Double, 
    trotterOrder : Int) : (Double, Double) {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nSpinOrbitals, fermionTermData, statePrepData, energyOffset) = qSharpData!;
    
    // Using a Product formula, also known as `Trotterization`, to
    // simulate the Hamiltonian.
    let (nQubits, (rescaleFactor, oracle)) = 
        TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // The operation that creates the trial state is defined here.
    // By default, greedy filling of spin-orbitals is used.
    let statePrep = PrepareTrialState(statePrepData, _);
    
    // Using the Robust Phase Estimation algorithm
    // of Kimmel, Low and Yoder.
    let phaseEstAlgorithm = RobustPhaseEstimation(nBitsPrecision, _, _);
    
    // This runs the quantum algorithm and returns a phase estimate.
    let estPhase = EstimateEnergy(nQubits, statePrep, oracle, phaseEstAlgorithm);
    
    // Now, obtain the energy estimate by rescaling the phase estimate
    // with the trotterStepSize. We also add the constant energy offset
    // to the estimated energy.
    let estEnergy = estPhase * rescaleFactor + energyOffset;
    
    // Return both the estimated phase and the estimated energy.
    return (estPhase, estEnergy);
}
```

<span data-ttu-id="103b7-122">Teraz można wywołać Q# kod z programu hosta.</span><span class="sxs-lookup"><span data-stu-id="103b7-122">You can now invoke the Q# code from the host program.</span></span> <span data-ttu-id="103b7-123">Poniższy kod w języku C# tworzy symulator i uruchamia `GetEnergyByTrotterization` się w celu uzyskania energii stanu ziemi.</span><span class="sxs-lookup"><span data-stu-id="103b7-123">The following C# code creates a full-state simulator and runs `GetEnergyByTrotterization` to obtain the ground state energy.</span></span>

```csharp
using (var qsim = new QuantumSimulator())
{
    // Specify the bits of precision desired in the phase estimation 
    // algorithm
    var bits = 7;

    // Specify the step size of the simulated time evolution. The step size needs to
    // be small enough to avoid aliasing of phases, and also to control the
    // error of simulation.
    var trotterStep = 0.4;

    // Choose the Trotter integrator order
    Int64 trotterOrder = 1;

    // As the quantum algorithm is probabilistic, run a few trials.

    // This may be compared to true value of
    Console.WriteLine("Exact molecular hydrogen ground state energy: -1.137260278.\n");
    Console.WriteLine("----- Performing quantum energy estimation by Trotter simulation algorithm");
    for (int i = 0; i < 5; i++)
    {
        // EstimateEnergyByTrotterization
        var (phaseEst, energyEst) = GetEnergyByTrotterization.Run(qsim, qSharpData, bits, trotterStep, trotterOrder).Result;
    }
}
```

<span data-ttu-id="103b7-124">Operacja zwraca dwa parametry:</span><span class="sxs-lookup"><span data-stu-id="103b7-124">The operation returns two parameters:</span></span> 

- <span data-ttu-id="103b7-125">`energyEst`jest szacunkową energią stanu ziemi i powinna być bliska `-1.137` średniej.</span><span class="sxs-lookup"><span data-stu-id="103b7-125">`energyEst` is the estimate of the ground state energy and should be close to `-1.137` on average.</span></span> 
- <span data-ttu-id="103b7-126">`phaseEst`jest fazą nieprzetworzoną zwracaną przez algorytm szacowania fazy.</span><span class="sxs-lookup"><span data-stu-id="103b7-126">`phaseEst` is the raw phase returned by the phase estimation algorithm.</span></span> <span data-ttu-id="103b7-127">Jest to przydatne do diagnozowania aliasu, gdy występuje z powodu `trotterStep` zbyt dużej wartości.</span><span class="sxs-lookup"><span data-stu-id="103b7-127">This useful for diagnosing aliasing when it occurs due to a `trotterStep` value that is too large.</span></span>
