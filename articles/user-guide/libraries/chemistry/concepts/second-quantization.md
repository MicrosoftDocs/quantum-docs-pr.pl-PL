---
title: Drugie podziału
description: Dowiedz się więcej na temat drugiego podejścia podziału do modelowania struktur elektronicznych w programowaniu Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: 6becd348f7b3957cb60b16bbd5a28228527e1d4c
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835812"
---
# <a name="second-quantization"></a><span data-ttu-id="5c986-103">Drugie podziału</span><span class="sxs-lookup"><span data-stu-id="5c986-103">Second Quantization</span></span>

<span data-ttu-id="5c986-104">Drugie podziału analizuje problem struktury elektronicznej przy użyciu innego obiektywu.</span><span class="sxs-lookup"><span data-stu-id="5c986-104">Second quantization looks at the problem of electronic structure through a different lens.</span></span>
<span data-ttu-id="5c986-105">Zamiast przypisywania poszczególnych $Nów _e $ Electrons do określonego stanu (lub orbity), druga podziału śledzi każdą wartość rzutu i przechowuje informacje o tym, czy w każdym z nich jest obecny numer elektronów, i w tym samym czasie automatycznie zapewnia właściwości symetrii odpowiedniej funkcji Wave.</span><span class="sxs-lookup"><span data-stu-id="5c986-105">Rather than assigning each of the $N_e$ electrons to a specific state (or orbital), second quantization tracks each orbital and stores whether there is an electron present in each of them and at the same time automatically ensures symmetry properties of the corresponding wave function.</span></span>
<span data-ttu-id="5c986-106">Jest to ważne, ponieważ umożliwia określenie modeli chemii Quantum bez konieczności symmetrizing stanu danych wejściowych (jak jest to wymagane dla fermions), a także, ponieważ druga podziału umożliwia symulowanie takich modeli przy użyciu małych komputerów Quantum.</span><span class="sxs-lookup"><span data-stu-id="5c986-106">This is important because it allows quantum chemistry models to be specified without having to worry about anti-symmetrizing the input state (as is required for fermions) and also because second quantization allows such models to be simulated using small quantum computers.</span></span>

<span data-ttu-id="5c986-107">Przykładem drugiego podziału w działaniu Przypuśćmy, że $ \ psi_0 \cdots \ psi_ {N-1} $ to orthonormal zestaw orbitals przestrzennych.</span><span class="sxs-lookup"><span data-stu-id="5c986-107">As an example of second quantization in action, let's assume that $\psi_0\cdots \psi_{N-1}$ are an orthonormal set of spatial orbitals.</span></span>
<span data-ttu-id="5c986-108">Te orbitals są wybrane do reprezentowania systemu tak dokładnie, jak to możliwe w ramach ograniczonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="5c986-108">These orbitals are chosen to represent the system as accurately as possible within the finite basis set considered.</span></span>
<span data-ttu-id="5c986-109">Typowym przykładem takich orbitals są niepodzielne orbitals, które tworzą eigenbasis dla atomów wodoru.</span><span class="sxs-lookup"><span data-stu-id="5c986-109">A common example of such orbitals are atomic orbitals which form an eigenbasis for the hydrogen atom.</span></span>
<span data-ttu-id="5c986-110">Ponieważ Electrons mają dwa stany pokrętła, dwa Electrons mogą być Crammed do każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="5c986-110">Because electrons have two spin states, two electrons can be crammed into each such spatial orbital.</span></span>
<span data-ttu-id="5c986-111">Oznacza to, że poprawne Stany podstawowe mają postać $ \ psi_ {0, \uparrow}, \ldots, \ psi_ {N-1, \uparrow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ WHERE $ \uparrow $ i $ \downarrow $ są etykietami, które określają dwa eigenstates stopnia swobody.</span><span class="sxs-lookup"><span data-stu-id="5c986-111">That is to say, the valid basis states are of the form $\psi_{0,\uparrow},\ldots,\psi_{N-1,\uparrow}, \psi_{0,\downarrow},\ldots,\psi_{N-1,\downarrow}$ where $\uparrow$ and $\downarrow$ are labels that specify the two eigenstates of the spin degree of freedom.</span></span>
<span data-ttu-id="5c986-112">Ten połączony indeks $ (j, \sigma) $ dla $ \sigma \In \{ \uparrow, \downarrow \} $ jest nazywany kręgiem, ponieważ przechowuje zarówno przestrzenne, jak i kąt obrotu.</span><span class="sxs-lookup"><span data-stu-id="5c986-112">This combined index of $(j,\sigma)$ for $\sigma \in \{\uparrow,\downarrow\}$ is called a spin-orbital because it stores both the spatial as well as the spin degree of freedom.</span></span>
<span data-ttu-id="5c986-113">W bibliotece chemii polecenie "orbitals" jest przechowywane w `SpinOrbital` strukturze danych i tworzone w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="5c986-113">In the chemistry library, spin-orbitals are stored in a `SpinOrbital` data structure, and are created as follows.</span></span>

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

<span data-ttu-id="5c986-114">Oznacza to, że możemy formalnie myśleć o podstawie dla elementu "obrót" i "przestrzenny" funkcji Wave jako $ \ psi_ {0} \cdots \ psi_ {2n-1} $, gdzie każdy indeks jest teraz wyliczeniem $ (j, \sigma) $.</span><span class="sxs-lookup"><span data-stu-id="5c986-114">This means that we can formally think of the basis for both the spin and spatial part of the wave function as $\psi_{0} \cdots \psi_{2N-1}$ where each of the indices now is an enumeration of a $(j,\sigma)$.</span></span>
<span data-ttu-id="5c986-115">Jedną z możliwych wyliczeniem jest $g (j, \sigma) = j + N\sigma ' $.</span><span class="sxs-lookup"><span data-stu-id="5c986-115">One possible enumeration is $g(j,\sigma) = j+N\sigma'$.</span></span>
<span data-ttu-id="5c986-116">Kolejną możliwym wyliczeniem jest $h (j, \sigma) = 2 \* j + \sigma $.</span><span class="sxs-lookup"><span data-stu-id="5c986-116">Another possible enumeration is $h(j,\sigma) = 2\*j + \sigma$.</span></span>
<span data-ttu-id="5c986-117">Biblioteka chemii Quantum może korzystać z tych konwencji, a w tym celu można utworzyć wystąpienie orbitals z takimi samymi kodowaniem.</span><span class="sxs-lookup"><span data-stu-id="5c986-117">The quantum chemistry library can use these conventions, and the spin-orbitals in such an encoding can be instantiated as follows.</span></span>

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

<span data-ttu-id="5c986-118">W przypadku systemów fermionic zasada wykluczenia Pauli zapobiega obecności więcej niż jednego elementu elektronu w jednym punkcie obrotu w tym samym czasie.</span><span class="sxs-lookup"><span data-stu-id="5c986-118">For fermionic systems, the Pauli exclusion principle prevents more than one electron from being present in any spin-orbital at the same time.</span></span>
<span data-ttu-id="5c986-119">Oznacza to, że możemy napisać dwa stany prawne dla $ \ psi_1 $ as \begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket {0} _1 & \Text{if $ \ psi_1 $ nie jest zajmowana} </span><span class="sxs-lookup"><span data-stu-id="5c986-119">This means that we can write the two legal states for $\psi_1$ as \begin{equation} \psi_1 \rightarrow \begin{cases} \ket{0}_1 & \text{if $\psi_1$ is not occupied,} </span></span>\\\
<span data-ttu-id="5c986-120">\ket {1} _1 & \Text{if $ \ psi_1 $ jest zajęta.}</span><span class="sxs-lookup"><span data-stu-id="5c986-120">\ket{1}_1 & \text{if $\psi_1$ is occupied.}</span></span> <span data-ttu-id="5c986-121">\end{Cases} \end{Equation} to rozwiązanie jest doskonałe dla komputerów z systemem Quantum, ponieważ oznacza to, że firma Microsoft może przechowywać zawód elektroniczny jako pojedynczy bit Quantum.</span><span class="sxs-lookup"><span data-stu-id="5c986-121">\end{cases} \end{equation} This encoding is great for quantum computers because it means that we can store the electronic occupation as a single quantum bit.</span></span>

<span data-ttu-id="5c986-122">Stany zawodności dla elementu $2N $ orbitals mogą być w podobny sposób przechowywane w $2N $ qubits.</span><span class="sxs-lookup"><span data-stu-id="5c986-122">The occupation states for the $2N$ spin orbitals can similarly be stored in $2N$ qubits.</span></span>
<span data-ttu-id="5c986-123">Przykładowo, jeśli $N = $2, wówczas stan $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="5c986-123">As an example, if $N=2$ then the state $$ \ket{0} \ket{1} \ket{1} \ket{0}, $$</span></span>

<span data-ttu-id="5c986-124">będzie odpowiadać za zajmowany przez pozostałe elementy orbitals $1 $ i $2 $.</span><span class="sxs-lookup"><span data-stu-id="5c986-124">would correspond to spin orbitals $1$ and $2$ being occupied with the remainder empty.</span></span>
<span data-ttu-id="5c986-125">Analogicznie, stan $ $ \ket {0} \equiv \ket {0} _ {0} \cdots \ket {0} _{N-1}, $ $</span><span class="sxs-lookup"><span data-stu-id="5c986-125">Similarly, the state $$ \ket{0} \equiv \ket{0}_{0} \cdots \ket{0}_{N-1}, $$</span></span>

<span data-ttu-id="5c986-126">nie ma Electrons i jest znany jako "stan próżniowy".</span><span class="sxs-lookup"><span data-stu-id="5c986-126">has no electrons and is known as the 'vacuum state'.</span></span>

<span data-ttu-id="5c986-127">Atrakcyjny efekt uboczny drugiego podziałuu polega na tym, że nie jest już konieczne jawne śledzenie przeciwsymetrii stanu Quantum.</span><span class="sxs-lookup"><span data-stu-id="5c986-127">A beautiful side-effect of second quantization is that we no longer have to explicitly keep track of the anti-symmetry of the quantum state.</span></span>
<span data-ttu-id="5c986-128">Wynika to z faktu, że w miarę jak zobaczymy, że antysymetria stanu reprezentuje zamiast nich reguły ochrony przed współdziałaniem operatorów, które tworzą i niszczą działania elektroniczne z kręgu.</span><span class="sxs-lookup"><span data-stu-id="5c986-128">This is because, as we will see, the anti-symmetry of the state represents itself instead through the anti-commutation rules of the operators that create and destroy electronic occupations of a spin orbital.</span></span>

## <a name="fermionic-operators"></a><span data-ttu-id="5c986-129">Operatory Fermionic</span><span class="sxs-lookup"><span data-stu-id="5c986-129">Fermionic operators</span></span>

<span data-ttu-id="5c986-130">Dwa podstawowe operatory, które działają na podstawie wektorów drugiej Quantized są znane jako operatory tworzenia i Annihilation.</span><span class="sxs-lookup"><span data-stu-id="5c986-130">The two fundamental operators that act on the second-quantized basis vectors are known as creation and annihilation operators.</span></span>
<span data-ttu-id="5c986-131">Te operatory wstawiają lub niszczą Electrons w określonej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="5c986-131">These operators insert or destroy electrons at a particular location.</span></span>
<span data-ttu-id="5c986-132">Są one oznaczone $a ^ \ dagger_j $ i $a _j $.</span><span class="sxs-lookup"><span data-stu-id="5c986-132">These are denoted $a^\dagger_j$ and $a_j$ respectively.</span></span>

<span data-ttu-id="5c986-133">Na przykład \begin{align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \quad a ^ \ dagger_1 \ket {1} _1 = 0, \quad A_1 \ket {0} _1 = 0, \quad A_1 \ket {1} _1 = \ket {0} _1.</span><span class="sxs-lookup"><span data-stu-id="5c986-133">For example, \begin{align} a^\dagger_1 \ket{0}_1 = \ket{1}_1,\quad a^\dagger_1 \ket{1}_1 = 0,\quad a_1 \ket{0}_1 = 0,\quad a_1 \ket{1}_1 = \ket{0}_1.</span></span>
<span data-ttu-id="5c986-134">\end{align} Pamiętaj, że w tym miejscu $a ^ \ dagger_1 \ket {1} _1 = 0 $ i $a _1 \ket _1 {0} $ Yield zero-Vector not $ \ket {0} _1 $.</span><span class="sxs-lookup"><span data-stu-id="5c986-134">\end{align} Note that here $a^\dagger_1 \ket{1}_1=0$ and $a_1 \ket{0}_1$ yield the zero-vector not $\ket{0}_1$.</span></span>
<span data-ttu-id="5c986-135">W związku z tym operatory te nie hermitian ani nie są jednostkowe.</span><span class="sxs-lookup"><span data-stu-id="5c986-135">Such operators are therefore neither Hermitian nor unitary.</span></span>
<span data-ttu-id="5c986-136">Reprezentujemy ogólne operatory tworzenia i Annihilation przy użyciu <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> typu.</span><span class="sxs-lookup"><span data-stu-id="5c986-136">We represent general creation and annihilation operators using the <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> type.</span></span>
<span data-ttu-id="5c986-137">Na przykład pojedynczy operator tworzenia jest reprezentowany jako poniżej.</span><span class="sxs-lookup"><span data-stu-id="5c986-137">For instance, a single creation operator is represented as follow.</span></span>

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

<span data-ttu-id="5c986-138">Również przy użyciu takich operatorów możemy wyrazić $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4}.</span><span class="sxs-lookup"><span data-stu-id="5c986-138">Also using such operators we can express $$ \ket{0} \ket{1} \ket{1} \ket{0} = a^\dagger_1 a^\dagger_2 \ket{0}^{\otimes 4}.</span></span>
<span data-ttu-id="5c986-139">$ $ Tę sekwencję operatorów można utworzyć w bibliotece symulacji hamiltonian przy użyciu kodu C#, który jest podobny do wielkości dwukierunkowego obrotu w jednym miejscu, jak powyżej:</span><span class="sxs-lookup"><span data-stu-id="5c986-139">$$ This sequence of operators would be constructed within the Hamiltonian simulation library using C# code that is similar to the single-spin orbital case considered above above:</span></span>
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

<span data-ttu-id="5c986-140">W przypadku systemu $k $ Fermions, w drugim podziału akcja operatora tworzenia $a ^ \ dagger_i $ jest określona przez $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $ $ i $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k} = 0, $ $, gdzie $S _i = \ sum_ {j<i} a ^ \ dagger_j a_j $ mierzy łączną liczbę Fermions, które są w stanie pojedynczej cząsteczek i mają indeks $j < i $.</span><span class="sxs-lookup"><span data-stu-id="5c986-140">For a system of $k$ Fermions, in second quantization the action of the creation operator $a^\dagger_i$ is given by $$ a^\dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k } = (-1)^{S_i} \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k}, $$ and $$ a^\dagger_i \ket{n_1, n_2, \ldots, 1_i, \ldots, n_k } = 0, $$ where $S_i = \sum_{j<i} a^\dagger_j a_j$ measures the total number of Fermions that are in the state of a single particle and that have an index $j < i$.</span></span>

<span data-ttu-id="5c986-141">Trzeci operator jest również często używany w drugim reprezentacje Quantized.</span><span class="sxs-lookup"><span data-stu-id="5c986-141">A third operator is also often used in second quantized representations.</span></span>
<span data-ttu-id="5c986-142">Ten operator jest znany jako operator Number i jest zdefiniowany przez \begin{Equation} n_i = a ^ \ dagger_i a_i.</span><span class="sxs-lookup"><span data-stu-id="5c986-142">This operator is known as the number operator and is defined by \begin{equation} n_i = a^\dagger_i a_i.</span></span>
<span data-ttu-id="5c986-143">\end{Equation} ten operator zlicza zawód danego kręgu, który ma na celu wypowiedzenie \begin{align} n_i \ket {0} _i &= 0 \ nonumber</span><span class="sxs-lookup"><span data-stu-id="5c986-143">\end{equation} This operator counts the occupation of a given spin orbital, which is to say \begin{align} n_i \ket{0}_i &= 0\nonumber</span></span>\\\
<span data-ttu-id="5c986-144">n_i \ket {1} _i &= \ket {1} _i.</span><span class="sxs-lookup"><span data-stu-id="5c986-144">n_i \ket{1}_i &= \ket{1}_i.</span></span>
<span data-ttu-id="5c986-145">\end{align} podobne do powyższych `FermionTerm` przykładów, ten operator liczby jest zbudowany w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="5c986-145">\end{align} Similar to the above `FermionTerm` examples, this number operator is constructed as follows.</span></span>
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

<span data-ttu-id="5c986-146">Subtlety powoduje, że w przypadku korzystania z operatorów tworzenia lub Annihilation w systemach fermionic.</span><span class="sxs-lookup"><span data-stu-id="5c986-146">A subtlety emerges though when using creation or annihilation operators in fermionic systems.</span></span>
<span data-ttu-id="5c986-147">Wymagane jest, aby wszystkie prawidłowe Stany Quantum były symetryczne w ramach wymiany etykiet.</span><span class="sxs-lookup"><span data-stu-id="5c986-147">We require that any valid quantum state is anti-symmetric under exchange of labels.</span></span>
<span data-ttu-id="5c986-148">Oznacza to, że $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 ^ \ dagger_2 \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="5c986-148">This means that $$ a^\dagger_2 a^\dagger_1 \ket{0} = -a^\dagger_1 a^\dagger_2 \ket{0}.</span></span>
<span data-ttu-id="5c986-149">$ $ Takie operatory są określane jako "leki" i ogólnie w odniesieniu do jakichkolwiek $i, j $ \begin{align} a ^ \ dagger_i ^ \ dagger_j =-(1-\ delta_ {i, j}) ^ \ dagger_j a ^ \ dagger_i, \quad ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.</span><span class="sxs-lookup"><span data-stu-id="5c986-149">$$ Such operators are said to 'anti-commute' and in general for any $i, j$ we have that \begin{align} a^\dagger_i a^\dagger_j  = -(1-\delta_{i,j})a^\dagger_j a^\dagger_i,\quad a^\dagger_i a_j =\delta_{i,j} - a_j a^\dagger_i.</span></span>
<span data-ttu-id="5c986-150">\end{align} w ten sposób następujące dwa <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> wystąpienia są uznawane za nierównoważne</span><span class="sxs-lookup"><span data-stu-id="5c986-150">\end{align} Thus the following two <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> instances are considered inequivalent</span></span>
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

<span data-ttu-id="5c986-151">Wymaganie, aby każdy z operatorów tworzenia nie pozostały w przypadku, gdy przy użyciu drugiej reprezentacji quantizedu nie nastąpiły wyzwania w związku z Fermions.</span><span class="sxs-lookup"><span data-stu-id="5c986-151">The requirement that each of the creation operators anti-commute means that using a second quantized representation does obviate the challenges faced by the anti-symmetry of Fermions.</span></span>
<span data-ttu-id="5c986-152">Zamiast tego wyzwanie zostanie ponowione w naszej definicji operatorów tworzenia.</span><span class="sxs-lookup"><span data-stu-id="5c986-152">Instead the challenge re-emerges in our definition of the creation operators.</span></span> 

<span data-ttu-id="5c986-153">Przy użyciu reguł antypoślizg niektóre `LadderSequence` wystąpienia rzeczywiście odpowiadają tej samej sekwencji operatorów fermionic, czasami do znaku minus.</span><span class="sxs-lookup"><span data-stu-id="5c986-153">Using the anti-commutation rules, some `LadderSequence` instances actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="5c986-154">Na przykład rozważmy hamiltonian $a _0 ^ \dagger a_1 ^ \dagger a_1 a_0 =-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 $.</span><span class="sxs-lookup"><span data-stu-id="5c986-154">For instance, consider the Hamiltonian $a_0^\dagger a_1^\dagger a_1 a_0 = - a_1^\dagger a_0^\dagger a_1 a_0$.</span></span>
<span data-ttu-id="5c986-155">W tym celu należy zdefiniować porządkowanie kanoniczne dla każdego z nich `FermionTerm` .</span><span class="sxs-lookup"><span data-stu-id="5c986-155">This motivates us to define a canonical ordering for every `FermionTerm`.</span></span>
<span data-ttu-id="5c986-156">Wszystkie `FermionTerm` są automatycznie umieszczane w porządku kanonicznym w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="5c986-156">Any `FermionTerm` is automatically put into canonical order as follows.</span></span>
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a><span data-ttu-id="5c986-157">Second-Quantized Fermionic hamiltonian</span><span class="sxs-lookup"><span data-stu-id="5c986-157">Second-Quantized Fermionic Hamiltonian</span></span>

<span data-ttu-id="5c986-158">Być może unsurprising, że hamiltonian w [modelach Quantum dla systemów elektronicznych](xref:microsoft.quantum.chemistry.concepts.quantummodels) można napisać pod warunkiem tworzenia i operatorów Annihilation.</span><span class="sxs-lookup"><span data-stu-id="5c986-158">It is perhaps unsurprising that the Hamiltonian in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) can be written in terms of creation and annihilation operators.</span></span>
<span data-ttu-id="5c986-159">W szczególności, jeśli $ \psi \_ j $ to orbitals kręgosłupa, które tworzą podstawę</span><span class="sxs-lookup"><span data-stu-id="5c986-159">In particular, if $\psi\_j$ are the spin orbitals that form the basis then</span></span>

<span data-ttu-id="5c986-160">\begin{Equation} \hat{H} = \sum \_ {pq} h { \_ pq} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} h \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ RA \_ s + h \_ {\textrm}, NUC: \label{EQ} totalHam, gdzie $h \_ {\end{Equation} \textrm} $ to energia jądrowa (jest to stała w ramach przybliżania ponoszonego przez NUC) i</span><span class="sxs-lookup"><span data-stu-id="5c986-160">\begin{equation} \hat{H} = \sum\_{pq} h\_{pq}a^\dagger\_p a\_q + \frac{1}{2}\sum\_{pqrs} h\_{pqrs}a^\dagger\_p a^\dagger\_q a\_ra\_s +h\_{\textrm nuc},\label{eq:totalHam} \end{equation} where $h\_{\textrm nuc}$ is the nuclear energy (which is a constant under the Born-Oppenheimer approximation) and</span></span>

<span data-ttu-id="5c986-161">\begin{align} h \_ {pq} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\Frac{\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3 \_ , \end{align}</span><span class="sxs-lookup"><span data-stu-id="5c986-161">\begin{align} h\_{pq} &= \int\_{-\infty}^\infty \psi^\*\_p(x\_1) \left(-\frac{\nabla^2}{2} +V(x\_1)\right)  \psi\_q(x\_1)\mathrm{d}^3x\_1, \end{align}</span></span>

<span data-ttu-id="5c986-162">gdzie $V (x) $ jest potencjalną wartość pola i</span><span class="sxs-lookup"><span data-stu-id="5c986-162">where $V(x)$ is the mean-field potential, and</span></span>

<span data-ttu-id="5c986-163">\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x 2) \psi \_ \_ \_ \_ \_ . \ Label {EQ: całeks} \mathrm{d}</span><span class="sxs-lookup"><span data-stu-id="5c986-163">\begin{align} h\_{pqrs} &= \int\_{-\infty}^\infty \int\_{-\infty}^\infty\psi\_p^\*(x\_1)\psi\_q^\*(x\_2) \left(\frac{1}{|x_1-x_2|} \right)\psi\_r(x\_2)\psi\_s(x\_1)\mathrm{d}^3x\_1\mathrm{d}^3x\_2.\label{eq:integrals} \end{align}</span></span>

<span data-ttu-id="5c986-164">Warunki $h \_ {pq} $ są określane jako całki jednokolorowe, ponieważ wszystkie te warunki obejmują tylko jedną electronsę i podobnie $h \_ {pqrs} $ są całkowitymi częściami dwuskładnikowymi.</span><span class="sxs-lookup"><span data-stu-id="5c986-164">The terms $h\_{pq}$ are referred to as one-electron integrals because all such terms only involve single electrons and likewise $h\_{pqrs}$ are the two-electron integrals.</span></span>
<span data-ttu-id="5c986-165">Są one nazywane całkami, ponieważ przetwarzanie wartości tych współczynników wymaga całkowitej liczby.</span><span class="sxs-lookup"><span data-stu-id="5c986-165">They are called integrals because computing the values of these coefficients requires an integral.</span></span>
<span data-ttu-id="5c986-166">Te warunki elektronów opisują energię kinetyczną poszczególnych Electrons i ich interakcje z polami elektrycznymi jądra.</span><span class="sxs-lookup"><span data-stu-id="5c986-166">The one electron terms describe the kinetic energy of the individual electrons and their interactions with the electric fields of the nuclei.</span></span>
<span data-ttu-id="5c986-167">Całkowite całki elektronów z drugiej strony opisują interakcje między Electrons.</span><span class="sxs-lookup"><span data-stu-id="5c986-167">The two-electron integrals on the other hand describe the interactions between the electrons.</span></span>

<span data-ttu-id="5c986-168">Intuition, co oznacza, że te warunki mogą być wydobyć od operatorów tworzenia i Annihilation, które składają się z każdego z nich.</span><span class="sxs-lookup"><span data-stu-id="5c986-168">An intuition for what these terms mean can be gleaned from the creation and annihilation operators that comprise each of them.</span></span>
<span data-ttu-id="5c986-169">Na przykład $h _ {pq} a ^ \ dagger_p a_q $ zawiera opis elektronów przeskoku od kręgu "$q" i "obracającą się $p $".</span><span class="sxs-lookup"><span data-stu-id="5c986-169">For example, $h_{pq}a^\dagger_p a_q$ describes the electron hopping from spin orbital $q$ to spin orbital $p$.</span></span>
<span data-ttu-id="5c986-170">Podobnie termin $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (dla różnych $p, q, r $ $) opisuje dwie Electrons w orbitals $r $ i $s $, a następnie kończy się w orbitalsu $p $ i $q $.</span><span class="sxs-lookup"><span data-stu-id="5c986-170">Similarly, the term $h_{pqrs} a^\dagger_p a^\dagger_q a_r a_s$ (for distinct $p,q,r,s$) describes two electrons in spin orbitals $r$ and $s$ scattering off of each other and ending up in spin orbitals $p$ and $q$.</span></span>
<span data-ttu-id="5c986-171">Jeśli $r = q $ i $p = s $ następnie $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = h_ {prrp} n_p n_r $ zapewnia karę energii skojarzoną z dwoma electronsami, ale nie opisują procesu dynamicznego.</span><span class="sxs-lookup"><span data-stu-id="5c986-171">If $r=q$ and $p=s$ then $h_{prrp} a^\dagger_p a^\dagger_r a_r a_p = h_{prrp} n_p n_r$ gives the energy penalty associated with the two electrons being near each other, but does not describe a dynamical process.</span></span>

<span data-ttu-id="5c986-172">Firma Microsoft może reprezentować takie Hamiltonians za pomocą `FermionHamiltonian` klasy, która jest zasadniczo listą zawierającą wszystkie żądane `FermionTerm` wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="5c986-172">We may represent such Hamiltonians using the `FermionHamiltonian` class, which is essentially a list containing all the desired `FermionTerm` instances.</span></span>
<span data-ttu-id="5c986-173">Ponieważ Hamiltonians są hermitian według definicji, indeksuje terminy przy użyciu bardziej wyspecjalizowanego typu, `HermitianFermionTerm` który również używa hermitian symetrii podczas sprawdzania, czy warunki są równoważne.</span><span class="sxs-lookup"><span data-stu-id="5c986-173">As Hamiltonians are Hermitian by definition, we index terms using the more specialized type `HermitianFermionTerm` that also uses Hermitian symmetry when checking whether terms are equivalent.</span></span>

<span data-ttu-id="5c986-174">Pozwól nam skonstruować kilka przykładów przykładowych.</span><span class="sxs-lookup"><span data-stu-id="5c986-174">Let us construct a few illustrative examples.</span></span>
<span data-ttu-id="5c986-175">Rozważmy hamiltonian $ \hat{H} = a_0 ^ \dagger a_1 + a_1 ^ \dagger a_0 $.</span><span class="sxs-lookup"><span data-stu-id="5c986-175">Consider the Hamiltonian $\hat{H} = a_0^\dagger a_1 + a_1^\dagger a_0$.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
<span data-ttu-id="5c986-176">Firma Microsoft może uprościć tę konstrukcję przy użyciu faktu, że operatory hamiltonian są operatorami hermitian.</span><span class="sxs-lookup"><span data-stu-id="5c986-176">We may simplify this construction using the fact that Hamiltonian operators are Hermitian operators.</span></span>
<span data-ttu-id="5c986-177">W przypadku dodawania warunków do hamiltonian przy użyciu `Add` , każdy termin nieHermitian, taki jak, `fermionTerm0` przyjmuje się, że jest sparowany z jego sprzężeniem hermitian.</span><span class="sxs-lookup"><span data-stu-id="5c986-177">When adding terms to the Hamiltonian using `Add`, any non-Hermitian term such as `fermionTerm0` is assumed to be paired with its Hermitian conjugate.</span></span>
<span data-ttu-id="5c986-178">W ten sposób Poniższy fragment kodu reprezentuje również ten sam hamiltonian:</span><span class="sxs-lookup"><span data-stu-id="5c986-178">Thus the following snippet also represents the same Hamiltonian:</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

<span data-ttu-id="5c986-179">Korzystając z reguł antypoślizg, niektóre `FermionTerm` wystąpienia w hamiltonian rzeczywiście odpowiadają tej samej sekwencji operatorów fermionic, czasami do znaku minus.</span><span class="sxs-lookup"><span data-stu-id="5c986-179">Using the anti-commutation rules, some `FermionTerm` instances in the Hamiltonian actually correspond to the same sequence of fermionic operators, sometimes up to a minus sign.</span></span>
<span data-ttu-id="5c986-180">Na przykład rozważmy hamiltonian $H = a_0 ^ \dagger a_1 ^ \dagger a_1 a_0-a_1 ^ \dagger a_0 ^ \dagger a_1 a_0 = 2a_0 ^ \dagger a_1 ^ \dagger a_1 a_0 $, który jest sumą warunków zbudowanych powyżej.</span><span class="sxs-lookup"><span data-stu-id="5c986-180">For instance, consider the Hamiltonian $H=a_0^\dagger a_1^\dagger a_1 a_0 - a_1^\dagger a_0^\dagger a_1 a_0 =2a_0^\dagger a_1^\dagger a_1 a_0$, which is a sum of terms constructed above.</span></span>
<span data-ttu-id="5c986-181">Być może nie zawsze jest jasne, że użytkownik ma równoważne warunki i dlatego mogą być dodawane do hamiltonian oddzielnie.</span><span class="sxs-lookup"><span data-stu-id="5c986-181">It may not always be clear to the user that these are equivalent terms, and so they may be added to the Hamiltonian separately.</span></span>
<span data-ttu-id="5c986-182">Alternatywnie można chcieć zmodyfikować już istniejące warunki w hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5c986-182">Alternatively, one may be interested in modifying already-existing terms in the Hamiltonian.</span></span>
<span data-ttu-id="5c986-183">W takich przypadkach firma Microsoft może łączyć równoważne warunki w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="5c986-183">In these cases, we may combine equivalent terms as follows.</span></span>
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
<span data-ttu-id="5c986-184">Łącząc współczynniki równoważnego terminu, zmniejszamy łączną liczbę warunków w hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5c986-184">By combining coefficients of equivalent terms, we reduce the total number of terms in the Hamiltonian.</span></span>
<span data-ttu-id="5c986-185">Później, zmniejsza to liczbę bram Quantum wymaganych do symulowania hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5c986-185">Later on, this reduces the number of quantum gates required to simulate the Hamiltonian.</span></span>

### <a name="internal-representation"></a><span data-ttu-id="5c986-186">Reprezentacja wewnętrzna</span><span class="sxs-lookup"><span data-stu-id="5c986-186">Internal Representation</span></span>

<span data-ttu-id="5c986-187">Fermionic hamiltonian z jednym i dwoma interakcjami jest reprezentowana w notacji drugiej-Quantized jako</span><span class="sxs-lookup"><span data-stu-id="5c986-187">A fermionic Hamiltonian with one- and two-body interactions is represented in second-quantized notation as</span></span>

<span data-ttu-id="5c986-188">$ $ \begin{align} H = \sum \_ {pq} h \_ {pq} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} H \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s}.</span><span class="sxs-lookup"><span data-stu-id="5c986-188">$$ \begin{align} H=\sum\_{pq}h\_{pq}a^\dagger\_{p}a\_{q}+\frac{1}{2}\sum\_{pqrs}h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}.</span></span>
<span data-ttu-id="5c986-189">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5c986-189">\end{align} $$</span></span>

<span data-ttu-id="5c986-190">W tej notacji istnieje maksymalnie $N ^ 2 + N ^ 4 $.</span><span class="sxs-lookup"><span data-stu-id="5c986-190">In this notation, there are at most $N^2+N^4$ coefficients.</span></span>
<span data-ttu-id="5c986-191">Jednak wiele z tych współczynników może być zebranych w zależności od tego samego operatora.</span><span class="sxs-lookup"><span data-stu-id="5c986-191">However, many of these coefficients may be collected as they correspond to the same operator.</span></span>
<span data-ttu-id="5c986-192">Na przykład w przypadku, gdy $p, q, r, s $ są oddzielnymi indeksami, firma Microsoft może używać zasad ochrony antyszpiegowskiej, aby pokazać, że: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger {p} a { \_ \_ r} a { \_ s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a { \_ r} \_ = \_ % \dagger {q} a {\dagger \_ {p} a {s} \_ a { \_ r}.</span><span class="sxs-lookup"><span data-stu-id="5c986-192">For instance, in the case where $p,q,r,s$ are distinct indices, we may use the anti-commutation rules to show that: $$ a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s} = -a^\dagger\_{q}a^\dagger\_{p}a\_{r}a\_{s} = -a^\dagger\_{p}a^\dagger\_{q}a\_{s}a\_{r} = a^\dagger\_{q}a^\dagger\_{p}a\_{s}a\_{r}.</span></span>
$$

<span data-ttu-id="5c986-193">Ponadto, jako $H $ jest hermitian, każdy $h operator fermionic hermitian \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $, ma hermitian koniugat, który znajduje się również w $H $.</span><span class="sxs-lookup"><span data-stu-id="5c986-193">Furthermore, as $H$ is Hermitian, every non-Hermitian fermionic operator, say $h\_{pqrs}a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}$, has a Hermitian conjugate that is also found in $H$.</span></span> <span data-ttu-id="5c986-194">W celu jednoznacznego indeksowania grup warunków scharakteryzowanych przez te symmetries definiujemy porządkowanie kanoniczne na indeksach $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ dowolnej sekwencji $n + m $ fermionic operatory $a ^ \dagger \_ {i \_ 1} \cdots \_ : ^ \dagger {i n \_ } a { \_ j 1 \_ } \cdots $AS \_ \_</span><span class="sxs-lookup"><span data-stu-id="5c986-194">In order to uniquely index groups of terms characterized by these symmetries, we define a canonical ordering on the indices $(i\_1,\cdots,i\_n,j\_1,\cdots,j\_m)$ of any sequence of $n+m$ fermionic operators $a^\dagger\_{i\_1}\cdots a^\dagger\_{i\_n}a\_{j\_1}\cdots a\_{j\_m}$as follows:</span></span>
-   <span data-ttu-id="5c986-195">Wszystkie operatory tworzenia $a ^ \dagger \_ {i \_ \cdot} $ są umieszczane przed wszystkimi operatorami Annihilation $a \_ {j \_ \cdot} $.</span><span class="sxs-lookup"><span data-stu-id="5c986-195">All creation operators $a^\dagger\_{i\_\cdot}$ are placed before all annihilation operators $a\_{j\_\cdot}$.</span></span>
-   <span data-ttu-id="5c986-196">Wszystkie indeksy operatora tworzenia są sortowane w kolejności rosnącej, czyli $i \_ 1< i \_ 2< \cdots < i \_ n $.</span><span class="sxs-lookup"><span data-stu-id="5c986-196">All creation operator indices are sorted in ascending order, that is $i\_1< i\_2< \cdots < i\_n$.</span></span>
-   <span data-ttu-id="5c986-197">Wszystkie indeksy operatora Annihilation są sortowane w kolejności malejącej, czyli $j \_ 1> j \_ 2 \cdots > j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="5c986-197">All annihilation operator indices are sorted in descending order, that is $j\_1> j\_2 \cdots > j\_m$.</span></span>
-   <span data-ttu-id="5c986-198">Indeks z lewej strony jest mniejszy niż lub równy indeksowi najwyższego poziomu, który jest $i \_ 1 \ Le j \_ m $.</span><span class="sxs-lookup"><span data-stu-id="5c986-198">The left-most index is less than or equal to the right-most index, that is $i\_1\le j\_m$.</span></span>

<span data-ttu-id="5c986-199">Daj nam zidentyfikować ten zestaw indeksów uporządkowanych w formie kanonicznej jako $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \In S \_ {n, m}.</span><span class="sxs-lookup"><span data-stu-id="5c986-199">Let us identify this set of canonically ordered indices as $$ \begin{align} (i\_1,\cdots,i\_n,j\_1,\cdots,j\_m) \in S\_{n,m}.</span></span>
<span data-ttu-id="5c986-200">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5c986-200">\end{align} $$</span></span>

<span data-ttu-id="5c986-201">W tym porządku kanonicznym fermionic hamiltonian może być wyrażony jako $ $ \begin{align} H = \sum \_ {(p, q) \In S \_ {1,1} } H " \_ {pq} \frac{a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, s) \In s \_ {2,2} } godz." \_ {pqrs} \frac{a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} + a ^ \dagger \_ {s} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ z odpowiednio przystosowanymi $h " \_ {pq} $ i $h" \_ {pqrs} $ ".</span><span class="sxs-lookup"><span data-stu-id="5c986-201">With this canonical ordering, the fermionic Hamiltonian may be expressed as $$ \begin{align} H=\sum\_{(p,q)\in S\_{1,1}}h'\_{pq}\frac{a^\dagger\_{p}a\_{q}+a^\dagger\_{q}a\_{p}}{2}+\sum\_{(p,q,r,s)\in S\_{2,2}}h'\_{pqrs}\frac{a^\dagger\_{p}a^\dagger\_{q}a\_{r}a\_{s}+a^\dagger\_{s}a^\dagger\_{r}a\_{q}a\_{p}}{2}, \end{align} $$ with suitably adapted one- and two-electron integrals $h'\_{pq}$ and $h'\_{pqrs}$, respectively.</span></span>

