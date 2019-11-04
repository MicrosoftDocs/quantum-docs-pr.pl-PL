---
title: Symulowanie hamiltonian Dynamics | Microsoft Docs
description: Symulowanie dokumentacji koncepcyjnej hamiltonian Dynamics
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: 905b03478d453e475fc1e49ea5f88dd0cd2704bc
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184070"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="85650-103">Symulowanie hamiltonian Dynamics</span><span class="sxs-lookup"><span data-stu-id="85650-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="85650-104">Gdy hamiltonian jest wyrażona jako suma operatorów elementarnych, można następnie kompilować do podstawowych operacji bram przy użyciu hosta dobrze znanych technik.</span><span class="sxs-lookup"><span data-stu-id="85650-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="85650-105">Trzy efektywne podejścia obejmują: Trotter — Suzukie formuły, liniowe kombinacje unitaries i qubitization.</span><span class="sxs-lookup"><span data-stu-id="85650-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="85650-106">Wyjaśniono te trzy podejścia poniżej i podano konkretne przykłady Q #, jak zaimplementować te metody przy użyciu biblioteki symulacji hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="85650-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="85650-107">Trotter — formuły Suzuki</span><span class="sxs-lookup"><span data-stu-id="85650-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="85650-108">Pomysłem za Trotter — formuły Suzuki są proste: wyrażenie hamiltonian jako sumę łatwego do symulowania Hamiltonians, a następnie przybliżenie całkowitego rozwoju jako sekwencji tych prostszych ewolucji.</span><span class="sxs-lookup"><span data-stu-id="85650-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="85650-109">W szczególności Let $H = \sum_{j = 1} ^ m H_j $ to hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="85650-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="85650-110">Następnie $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \prod_{j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, co oznacza, że jeśli $t \ll $1, błąd w tym przybliżeniu będzie nieznaczny.</span><span class="sxs-lookup"><span data-stu-id="85650-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="85650-111">Należy pamiętać, że jeśli $e ^ {-i H t} $ były zwykłą wartością wykładniczą, błąd w tym przybliżeniu nie będzie $O (m ^ 2 t ^ 2) $: wartość będzie równa zero.</span><span class="sxs-lookup"><span data-stu-id="85650-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="85650-112">Ten błąd występuje, ponieważ $e ^ {-iHt} $ jest operatorem wykładniczym i w związku z tym występuje błąd podczas korzystania z tej formuły ze względu na fakt, że $H _j $ terms nie korzystają (*tj.* $H _j H_k \Ne H_k H_j $).</span><span class="sxs-lookup"><span data-stu-id="85650-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="85650-113">Jeśli $t $ jest duże, Trotter — formuły Suzuki mogą być używane w celu dokładnego symulowania dynamiki przez podzielenie go na sekwencję krótkich etapów czasu.</span><span class="sxs-lookup"><span data-stu-id="85650-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="85650-114">Niech $r $ to liczba kroków podejmowanych w czasie rozwoju.</span><span class="sxs-lookup"><span data-stu-id="85650-114">Let $r$ be the number of steps taken in the time evolution.</span></span>
<span data-ttu-id="85650-115">Następnie mamy $ $ e ^ {-i\sum_ {j = 1} ^ m H_j t} = \left (\prod_{j = 1} ^ m e ^ {-iH_j t/r} \ Right) ^ r + O (m ^ 2 t ^ 2/r), $ $, co oznacza, że jeśli $r $ skaluje się jako $m ^ 2 t ^ 2/1/Epsilon $, błąd może zostać wykonany z najwyżej $ \epsilon $ dla dowolnego $ \epsilon > 0 $.</span><span class="sxs-lookup"><span data-stu-id="85650-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="85650-116">Dokładniejsze przybliżenia mogą być kompilowane przez konstruowanie sekwencji wykładniczych operatorów w taki sposób, że warunki błędu anulują się.</span><span class="sxs-lookup"><span data-stu-id="85650-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="85650-117">Najprostsza taka formuła, symetryczna formuła Trotter lub podział Strang, przyjmuje postać $ $ U_1 (t) = \prod_{j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-iHt} + O (m ^ 3 t ^ 3), $ $, który może być mniejszy niż $ \epsilon $ dla dowolnego $ \epsilon > 0 $, wybierając pozycję $ r $ do skalowania jako $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $.</span><span class="sxs-lookup"><span data-stu-id="85650-117">The simplest such formula, the symmetric Trotter formula or Strang splitting, takes the form $$ U_1(t) =\prod_{j=1}^m e^{-iH_j t/2}\prod_{j=m}^1 e^{-iH_j t} = e^{-iHt} + O(m^3 t^3), $$ which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="85650-118">Nawet w przypadku formuł Trotter o wyższej kolejności można utworzyć na podstawie $U _1 $.</span><span class="sxs-lookup"><span data-stu-id="85650-118">Even higher-order Trotter formulas can be constructed based on $U_1$.</span></span>
<span data-ttu-id="85650-119">Najprostszą jest następująca czwarta formuła Order, pierwotnie wprowadzone przez Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-iHt} + O (m ^ 5t ^ 5), $ $, gdzie $s _1 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="85650-119">The simplest is the following fourth order formula, originally introduced by Suzuki: $$ U_2(t) = U_1^2(s_1t) U_1([1-4s_1]t)U_1^2(s_1 t) = e^{-iHt} +O(m^5t^5), $$ where $s_1 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="85650-120">Ogólnie rzecz biorąc, szybkie i wysoce uporządkowane formuły mogą być w podobny sposób skonstruowane. jednak koszty wynikające z używania bardziej złożonych integratorów często są większe niż w czwartej kolejności w przypadku większości praktycznych problemów.</span><span class="sxs-lookup"><span data-stu-id="85650-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="85650-121">Aby powyższe strategie działały, musimy mieć metodę symulowania szerokiej klasy $e ^ {-iH_j t} $.</span><span class="sxs-lookup"><span data-stu-id="85650-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="85650-122">Najprostszą rodziną Hamiltonians i raczej najbardziej przydatną w tym miejscu może być operator Pauli.</span><span class="sxs-lookup"><span data-stu-id="85650-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="85650-123">Operatory Pauli można łatwo symulować, ponieważ mogą być ukośne przy użyciu operacji Clifford (które są bramami standardowymi w ramach przetwarzania Quantum).</span><span class="sxs-lookup"><span data-stu-id="85650-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="85650-124">Po przeprowadzeniu przekątnej ich eigenvalues można znaleźć, obliczając parzystość qubits, na której działają.</span><span class="sxs-lookup"><span data-stu-id="85650-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="85650-125">Na przykład $ $ e ^ {-iX\otimes X t} = (H\otimes H) e ^ {-iZ\otimes Z t} (H\otimes H), $ $ WHERE $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="85650-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="85650-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="85650-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="85650-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="85650-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="85650-128">0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="85650-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="85650-129">$ $ Tutaj $e ^ {-iHt} \ket{00} = e ^ {IT} \ket{00}$ i $e ^ {-iHt} \ket{01} = e ^ {-IT} \ket{01}$, który może być widoczny bezpośrednio jako konsekwencja, że parzystość $0 $ wynosi $0 $, a parzystość ciągu bitowego $1 $ to $1 $.</span><span class="sxs-lookup"><span data-stu-id="85650-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="85650-130">Wykładnicze operatory Pauli można zaimplementować bezpośrednio w Q # przy użyciu operacji <xref:microsoft.quantum.primitive.exp>:</span><span class="sxs-lookup"><span data-stu-id="85650-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.primitive.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies e^{- i X \otimes X t} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="85650-131">W przypadku Fermionic Hamiltonians, w której [dekompozycja Jordanii – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) , wygodnie mapuje hamiltonian na sumę operatorów Pauli.</span><span class="sxs-lookup"><span data-stu-id="85650-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="85650-132">Oznacza to, że powyższe podejście można łatwo dostosować do symulowania chemii.</span><span class="sxs-lookup"><span data-stu-id="85650-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="85650-133">Zamiast ręcznego zapętlenia wszystkich Paulich w reprezentacji Jordania-Wigner, poniżej przedstawiono prosty przykład sposobu wykonywania takich symulacji w ramach chemii.</span><span class="sxs-lookup"><span data-stu-id="85650-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="85650-134">Naszym punktem początkowym jest [kodowanie Jordania – Wigner](xref:microsoft.quantum.chemistry.concepts.jordanwigner) Fermionic hamiltonian, wyrażone w kodzie jako wystąpienie klasy `JordanWignerEncoding`.</span><span class="sxs-lookup"><span data-stu-id="85650-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="85650-135">Ten format Wigner reprsentation, który jest zużywany przez algorytmy symulacji Q # jest typem zdefiniowanym przez użytkownika `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="85650-135">This format of the Jordan–Wigner reprsentation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="85650-136">W obszarze Q # ten format jest przesyłany do wygodnej funkcji `TrotterStepOracle`, która zwraca operator zbliżający się czas i ewolucji przy użyciu integratora Trotter — Suzuki, oprócz innych parametrów wymaganych do wykonania.</span><span class="sxs-lookup"><span data-stu-id="85650-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="85650-137">Ponadto ta implementacja stosuje pewne optymalizacje omówione w [symulacji struktury elektronicznej Hamiltonians przy użyciu komputerów Quantum](https://arxiv.org/abs/1001.3855) i [ulepszanie algorytmów Quantum dla chemii Quantum](https://arxiv.org/abs/1403.1539) , aby zminimalizować liczbę wymagane są rotacje qubit, a także zmniejszenie błędów symulacji.</span><span class="sxs-lookup"><span data-stu-id="85650-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="85650-138">Qubitization</span><span class="sxs-lookup"><span data-stu-id="85650-138">Qubitization</span></span>

<span data-ttu-id="85650-139">Qubitization jest alternatywnym podejściem do symulacji, która używa koncepcji z przechodzenia Quantum do symulowania jednostek Quantum Dynamics.</span><span class="sxs-lookup"><span data-stu-id="85650-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="85650-140">Chociaż qubitization wymaga więcej qubits niż Trotter formuł, Metoda niesie obietnice zwiększenia optymalne skalowanie z czasem ewolucji i odporność na błędy.</span><span class="sxs-lookup"><span data-stu-id="85650-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="85650-141">Z tego względu jest to preferowana metoda symulowania hamiltonian Dynamics w ogólności i rozwiązywania problemu ze strukturą elektroniczną.</span><span class="sxs-lookup"><span data-stu-id="85650-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="85650-142">Na wysokim poziomie qubitization wykonuje się w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="85650-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="85650-143">Najpierw pozwól $H = \sum_j h_j H_j $ for units and hermitian $H _j $ i $h _j \ GE $0.</span><span class="sxs-lookup"><span data-stu-id="85650-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="85650-144">Wykonując parę odbicia, qubitization implementuje operator, który jest odpowiednikiem $ $W = e ^ {\Pm i \cos ^{-1}(H/| H | _1)}, $ $, gdzie $ | H | _1 = \sum_j | h_j | $.</span><span class="sxs-lookup"><span data-stu-id="85650-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="85650-145">Następny krok polega na przekroczeniu wartości eigenvalues operatora przeszukiwania z $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, gdzie $E _k $ to eigenvalues $H $, $e ^ {-iE_k t} $.</span><span class="sxs-lookup"><span data-stu-id="85650-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="85650-146">Można to osiągnąć przy użyciu różnych metod przekształcania wartości pojedynczej klasy Quantum, w tym [przetwarzania sygnałów Quantum](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="85650-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="85650-147">Alternatywnie, jeśli pożądane są tylko ilości statyczne (na przykład energia stanu ziemi hamiltonian), wystarcza do zastosowania [szacowania fazy](xref:microsoft.quantum.libraries.characterization) bezpośrednio do $W $, aby oszacować energię stanu ziemi z wyniku, przyjmując cosinus wyniku.</span><span class="sxs-lookup"><span data-stu-id="85650-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="85650-148">Jest to istotne, ponieważ umożliwia przekształcenie widma klasycznego, a nie użycie metody transformacji pojedynczej wartości.</span><span class="sxs-lookup"><span data-stu-id="85650-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="85650-149">Na bardziej szczegółowym poziomie implementacja qubitization wymaga dwóch podprocedur, które udostępniają interfejsy dla hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="85650-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="85650-150">W przeciwieństwie do metod Trotter – Suzuki, te podprocedury są nie klasyczne, a ich implementacja będzie wymagała użycia logarithmically więcej qubits niż jest to wymagane dla symulacji opartej na Trotter.</span><span class="sxs-lookup"><span data-stu-id="85650-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="85650-151">Pierwsza podprocedura Quantum wykorzystywana przez qubitization jest nazywana $ \operatorname{Select} $ i jest zastosowana do uzyskania \begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{Equation}, gdzie każda $H _j $ jest przyjęta jako hermitian i jednostki.</span><span class="sxs-lookup"><span data-stu-id="85650-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="85650-152">Chociaż może to być restrykcyjne, należy odwołać, że operatory Pauli są hermitian i jednostkowe, a więc aplikacje, takie jak symulowanie chemii Quantum, naturalnie są w tej strukturze.</span><span class="sxs-lookup"><span data-stu-id="85650-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="85650-153">Operacja $ \operatorname{Select} $, prawdopodobnie Surprisingly, jest w rzeczywistości operacją odbicia.</span><span class="sxs-lookup"><span data-stu-id="85650-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="85650-154">Może to być widoczne z faktu, że $ \operatorname{Select} ^ 2 \ KET {j} \ket{\psi} = \ket{j} \ket{\psi} $, ponieważ każdy $H _j $ jest jednostką i hermitian, a tym samym eigenvalues $ \Pm $1.</span><span class="sxs-lookup"><span data-stu-id="85650-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="85650-155">Druga podprocedura jest nazywana $ \operatorname{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="85650-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="85650-156">Podczas gdy operacja Select zapewnia spójny dostęp do każdego z hamiltonian warunków $H _j $ procedura Prepare zapewnia metodę uzyskiwania dostępu do współczynników $h _j $, \begin{Equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{ | h | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="85650-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="85650-157">\end{Equation} następnie przy użyciu wielokrotnie kontrolowanej bramy fazy, zobaczymy, że $ $ \Lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \Text{if} x = 0 </span><span class="sxs-lookup"><span data-stu-id="85650-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="85650-158">\ket{x} & \Text{Otherwise} \end{cases}.</span><span class="sxs-lookup"><span data-stu-id="85650-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="85650-159">Operacja $ \operatorname{Prepare} $ nie jest używana bezpośrednio w qubitization, ale raczej służy do implementowania odbicia o stanie, który $ \operatorname{Prepare} $ tworzy $ $ \begin{align} R &amp; = 1-2 \ operatorname {Prepare} \ket{0}\bra @no_ _t_2_ \operatorname{Prepare} ^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="85650-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="85650-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="85650-160">\end{align} $$</span></span>

<span data-ttu-id="85650-161">Operator przeszukiwania, $W $, może być wyrażony w postaci $ \operatorname{Select} $ i $R $ operacji as $ $ W = \operatorname{Select} R, $ $, który ponownie można zobaczyć, aby zaimplementować operatora, który jest równoważny (do isometry), aby $e ^ {\Pm i \cos ^{-1}(H/| H | _1)} $.</span><span class="sxs-lookup"><span data-stu-id="85650-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="85650-162">Te podprocedury można łatwo skonfigurować w programie Q #.</span><span class="sxs-lookup"><span data-stu-id="85650-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="85650-163">Przykładowo Rozważmy proste qubit poprzecznie Ising hamiltonian, gdzie $H = X_1 + X_2 + Z_1 Z_2 $.</span><span class="sxs-lookup"><span data-stu-id="85650-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="85650-164">W takim przypadku kod Q # implementujący operację $ \operatorname{Select} $ jest wywoływany przez <xref:microsoft.quantum.canon.multiplexoperations>, podczas gdy operacja $ \operatorname{Prepare} $ może być implementowana przy użyciu <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span><span class="sxs-lookup"><span data-stu-id="85650-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="85650-165">Przykład, który obejmuje symulowanie modelu Hubbard, można znaleźć jako [przykład Q #](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).</span><span class="sxs-lookup"><span data-stu-id="85650-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/Microsoft/Quantum/tree/master/Samples/src/HubbardSimulation).</span></span>

<span data-ttu-id="85650-166">Ręczne określenie tych kroków dla dowolnego problemu chemicznego będzie wymagało dużej nakładu pracy, które można uniknąć przy użyciu biblioteki chemicznej.</span><span class="sxs-lookup"><span data-stu-id="85650-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="85650-167">Podobnie jak w przypadku algorytmu symulacji Trotter – Suzuki powyżej, `JordanWignerEncodingData` jest przenoszona do funkcji wygodne `QubitizationOracle`, która zwraca operator przechodzenia, oprócz innych parametrów wymaganych do wykonania.</span><span class="sxs-lookup"><span data-stu-id="85650-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operatrion.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="85650-168">Ważne <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> implementacji ma zastosowanie do dowolnego Hamiltoniansu określonego jako liniowa kombinacja ciągów Pauli.</span><span class="sxs-lookup"><span data-stu-id="85650-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="85650-169">Wersja zoptymalizowana pod kątem symulacji chemicznej jest wywoływana przy użyciu <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span><span class="sxs-lookup"><span data-stu-id="85650-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="85650-170">Ta wersja jest zoptymalizowana pod kątem zminimalizowania liczby bram T wykorzystujących techniki omówione w temacie [kodowanie elektronicznych widm w obwodach Quantum przy użyciu liniowej złożoności T](https://arxiv.org/abs/1805.03662).</span><span class="sxs-lookup"><span data-stu-id="85650-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
