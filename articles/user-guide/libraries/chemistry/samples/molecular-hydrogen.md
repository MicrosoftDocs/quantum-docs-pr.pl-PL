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
ms.openlocfilehash: 05506f4099de754cd02d81fbd9200f2de091e37e
ms.sourcegitcommit: 8256ff463eb9319f1933820a36c0838cf1e024e8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90759736"
---
# <a name="obtaining-energy-level-estimates"></a>Uzyskiwanie szacunkowych poziomów energii
Oszacowanie wartości poziomów energii jest jednym z głównych zastosowań chemii Quantum. W tym artykule opisano, jak można wykonać to dla kanonicznego przykładu wodoru. Przykład przywoływany w tej sekcji znajduje się [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogen) w repozytorium próbek chemii. Jest to przykładowy przykład wizualizacji, który przedstawia dane wyjściowe [`MolecularHydrogenGUI`](https://github.com/microsoft/Quantum/tree/main/samples/chemistry/MolecularHydrogenGUI) .

## <a name="estimating-the-energy-values-of-molecular-hydrogen"></a>Oszacowanie wartości energetycznych wodoru

Pierwszym krokiem jest utworzenie hamiltonian reprezentującego wodór molekularny. Chociaż można utworzyć ten program przy użyciu narzędzia NWChem, w przypadku zwięzłości, ten przykład ręcznie dodaje warunki hamiltonian.

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

Symulowanie hamiltonian wymaga przekonwertowania operatorów Fermion na operatory qubit. Ta konwersja jest wykonywana za pomocą kodowania Jordania-Wigner w następujący sposób:

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

Następnie Przekaż `qSharpData` , który reprezentuje hamiltonian, do `TrotterStepOracle` funkcji. `TrotterStepOracle` zwraca operację Quantum, która przybliży ewolucję hamiltonian w czasie rzeczywistym. Aby uzyskać więcej informacji, zobacz [symulowanie hamiltonian Dynamics](xref:microsoft.quantum.chemistry.concepts.simulationalgorithms).

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

W tym momencie można użyć [algorytmów szacowania fazy](xref:microsoft.quantum.libraries.characterization) standardowej biblioteki, aby poznać energię stanu ziemi przy użyciu poprzedniej symulacji. Wymaga to przygotowania dobrego zbliżania do stanu ziemi Quantum. Sugestie dotyczące tych przybliżeń znajdują się w [`Broombridge`](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) schemacie. Niemniej jednak te sugestie, domyślne podejście dodaje wiele Electrons, `hamiltonian.NElectrons` Aby greedily zminimalizować okresy świetlne jednego z nich. Funkcje i operacje szacowania fazy są dostępne w notacji DocFX w przestrzeni nazw [Microsoft. Quantum. charakteryzującą](xref:microsoft.quantum.characterization) .

Poniższy fragment kodu przedstawia sposób, w jaki dane wyjściowe ewolucji w czasie rzeczywistym przez bibliotekę symulacji chemicznej integrują się z oszacowaniem fazy Quantum.

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

Teraz można wywołać Q# kod z programu hosta. Poniższy kod w języku C# tworzy symulator i uruchamia `GetEnergyByTrotterization` się w celu uzyskania energii stanu ziemi.

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

Operacja zwraca dwa parametry: 

- `energyEst` jest szacunkową energią stanu ziemi i powinna być bliska `-1.137` średniej. 
- `phaseEst` jest fazą nieprzetworzoną zwracaną przez algorytm szacowania fazy. Jest to przydatne do diagnozowania aliasu, gdy występuje z powodu `trotterStep` zbyt dużej wartości.
