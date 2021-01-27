---
title: Skorelowane funkcje falowe
description: Dowiedz się więcej na temat korelacji dynamicznych i niedynamicznych w wavefunctions przy użyciu biblioteki chemii Microsoft Quantum.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.multireference
no-loc:
- Q#
- $$v
ms.openlocfilehash: ab3d90d79c7c14a1ef5b3aa833df49be186f3dd7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856269"
---
# <a name="correlated-wavefunctions"></a><span data-ttu-id="5a800-103">Skorelowane funkcje falowe</span><span class="sxs-lookup"><span data-stu-id="5a800-103">Correlated wavefunctions</span></span>

<span data-ttu-id="5a800-104">W przypadku wielu systemów, szczególnie tych znajdujących się w sąsiedztwie równowagi, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teoretycznie zapewnia jakościowy opis właściwości molekularnych za pomocą jednoelementowego stanu odwołania.</span><span class="sxs-lookup"><span data-stu-id="5a800-104">For many systems, particularly those near the equilibrium geometry, [Hartree–Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) theory provides a qualitative description of molecular properties through a single-determinant reference state.</span></span> <span data-ttu-id="5a800-105">Jednak w celu osiągnięcia dokładności ilościowej należy również wziąć pod uwagę wpływ korelacji.</span><span class="sxs-lookup"><span data-stu-id="5a800-105">However, in order to achieve quantitative accuracy, one must also consider correlation effects.</span></span> 

<span data-ttu-id="5a800-106">W tym kontekście ważne jest dinstinguish między korelacją dynamiczną i niedynamiczną.</span><span class="sxs-lookup"><span data-stu-id="5a800-106">In this context, it is important to dinstinguish between dynamic and non-dynamic correlations.</span></span>
<span data-ttu-id="5a800-107">Dynamiczne korelacje powstają od tendencji Electrons do pozostania, takich jak z powodu międzyelektronicznego napędu.</span><span class="sxs-lookup"><span data-stu-id="5a800-107">Dynamical correlations arise from the tendency of electrons to stay apart, such as due to interelectronic repulsion.</span></span> <span data-ttu-id="5a800-108">Ten efekt może być modelowany przez rozważenie excitations Electrons z stanu odwołania.</span><span class="sxs-lookup"><span data-stu-id="5a800-108">This effect can be modelled by considering excitations of electrons out of the reference state.</span></span> <span data-ttu-id="5a800-109">Niedynamiczne korelacje powstają, gdy wavefunction jest zdominowany przez dwie lub więcej konfiguracji w kolejności zerowego, nawet w celu uzyskania tylko jakościowego opisu systemu.</span><span class="sxs-lookup"><span data-stu-id="5a800-109">Non-dynamic correlations arise when the wavefunction is dominated by two or more configurations at zeroth order, even to achieve only a qualitative description of the system.</span></span>
<span data-ttu-id="5a800-110">To wymaga nadłożenia znaczników i jest przykładem wieloodwołaniaowej wavefunction.</span><span class="sxs-lookup"><span data-stu-id="5a800-110">This necessitates a superposition of determinants and is an example of a multireference wavefunction.</span></span>

<span data-ttu-id="5a800-111">Biblioteka chemii umożliwia określenie zerowego Order wavefunction dla problemu wieloreferencyjnego jako nadpozycji znaczników.</span><span class="sxs-lookup"><span data-stu-id="5a800-111">The chemistry library provides a way to specify a zeroth order wavefunction for the multireference problem as a superposition of determinants.</span></span> <span data-ttu-id="5a800-112">To podejście, które dzwonimy do wavefunctions rozrzedzenia, jest skuteczne, gdy tylko kilka składników wystarcza do określenia nadpozycji.</span><span class="sxs-lookup"><span data-stu-id="5a800-112">This approach, which we call sparse multireference wavefunctions, is effective when only a few components suffice to specify the superposition.</span></span> <span data-ttu-id="5a800-113">Biblioteka udostępnia również metodę, aby uwzględnić dynamiczne korelacje na jednym wyznaczniku, za pośrednictwem uogólnionego, połączonego z jednostką ansatz.</span><span class="sxs-lookup"><span data-stu-id="5a800-113">The library also provides a method to include dynamic correlations on top of a single-determinant reference via the generalized unitary coupled-cluster ansatz.</span></span> <span data-ttu-id="5a800-114">Ponadto tworzy również obwodów Quantum, które generują te Stany na komputerze Quantum.</span><span class="sxs-lookup"><span data-stu-id="5a800-114">Furthermore, it also constructs quantum circuits that generate these states on a quantum computer.</span></span> <span data-ttu-id="5a800-115">Te Stany mogą być określone w [schemacie Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)i udostępniamy również funkcje ręcznego określania tych stanów za pomocą biblioteki chemicznej.</span><span class="sxs-lookup"><span data-stu-id="5a800-115">These states may be specified in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), and we also provide the functionality to manually specify these states through the chemistry library.</span></span>

## <a name="sparse-multi-reference-wavefunction"></a><span data-ttu-id="5a800-116">Rozrzedzony wavefunction wiele odwołań</span><span class="sxs-lookup"><span data-stu-id="5a800-116">Sparse multi-reference wavefunction</span></span>
<span data-ttu-id="5a800-117">Stan wieloodwołania $ \ket{\ psi_ {\RM {MCSCF}}} $ może być jawnie określony jako liniowa kombinacja $N $-elektron Slater determininants.</span><span class="sxs-lookup"><span data-stu-id="5a800-117">A multi-reference state $\ket{\psi_{\rm {MCSCF}}}$ may be specified explicitly as a linear combination of $N$-electron Slater determininants.</span></span>
<span data-ttu-id="5a800-118">\begin{align} \ket{\ psi_ {\RM {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots {dagger_} \ket {0} .</span><span class="sxs-lookup"><span data-stu-id="5a800-118">\begin{align} \ket{\psi_{\rm {MCSCF}}} \propto \sum_{i_1 < i_2 < \cdots < i_N} \lambda_{i_1,i_2,\cdots,i_N} a^\dagger_{i_1}a^\dagger_{i_2}\cdots a^\dagger_{i_N}\ket{0}.</span></span>
<span data-ttu-id="5a800-119">\end{align} na przykład stan $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ można określić w bibliotece chemii w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="5a800-119">\end{align} For example, the state $\propto(0.1 a^\dagger_1a^\dagger_2a^\dagger_6 - 0.2 a^\dagger_2a^\dagger_1a^\dagger_5)\ket{0}$ may be specified in the chemistry library as follows.</span></span>
```csharp
// Create a list of tuples where the first item of each 
// tuple are indices to the creation operators acting on the
// vacuum state, and the second item is the coefficient
// of that basis state.
var superposition = new[] {
    (new[] {1, 2, 6}, 0.1),
    (new[] {2, 1, 5}, -0.2) };

// Create a fermion wavefunction object that represents the superposition.
var wavefunction = new FermionWavefunction<int>(superposition);
```
<span data-ttu-id="5a800-120">Ta jawna reprezentacja składników położeniu jest skuteczna, gdy należy określić tylko kilka składników.</span><span class="sxs-lookup"><span data-stu-id="5a800-120">This explicit representation of the superposition components is effective when only a few components need to be specified.</span></span> <span data-ttu-id="5a800-121">Należy unikać używania tej reprezentacji, gdy wiele składników jest wymaganych do dokładnego przechwycenia żądanego stanu.</span><span class="sxs-lookup"><span data-stu-id="5a800-121">One should avoid using this representation when many components are required to accurately capture the desired state.</span></span> <span data-ttu-id="5a800-122">Przyczyną tego jest koszt usługi w ramach obwodu Quantum, który przygotowuje ten stan na komputerze z systemem Quantum, co oznacza, że skaluje się co najmniej liniowo przy użyciu liczby składników podpozycji, a najwyżej jedna z nich jest równa jednej kombinacji amplitud.</span><span class="sxs-lookup"><span data-stu-id="5a800-122">The reason for this is the gate cost of quantum circuit that prepares this state on a quantum computer, which scales at least linearly with the number of superposition components, and at most quadratically with the one-norm of the superposition amplitudes.</span></span>

## <a name="unitary-coupled-cluster-wavefunction"></a><span data-ttu-id="5a800-123">Połączone z jednostką — wavefunction klastra</span><span class="sxs-lookup"><span data-stu-id="5a800-123">Unitary coupled-cluster wavefunction</span></span>
<span data-ttu-id="5a800-124">Istnieje również możliwość określenia jednostki powiązanej-Cluster wavefunction $ \ket{\ psi_ {\RM {UCC}}} $ przy użyciu biblioteki chemistery.</span><span class="sxs-lookup"><span data-stu-id="5a800-124">It is also possible to specify a unitary coupled-cluster wavefunction $\ket{\psi_{\rm {UCC}}}$ using the chemistery library.</span></span> <span data-ttu-id="5a800-125">W takiej sytuacji mamy jednoelementowy stan odwołania, powiedzmy, $ \ket{\ psi_ {\rm{SCF}}} $.</span><span class="sxs-lookup"><span data-stu-id="5a800-125">In this situation, we have a single-determinant reference state, say, $\ket{\psi_{\rm{SCF}}}$.</span></span> <span data-ttu-id="5a800-126">Składniki połączonego z jednostką wavefunction klastra są następnie określone jako niejawne przez operatora jednostki działającej na stanie odwołania.</span><span class="sxs-lookup"><span data-stu-id="5a800-126">The components of the unitary coupled-cluster wavefunction are then specified implicity through a unitary operator acting on a reference state.</span></span>
<span data-ttu-id="5a800-127">Ten operator jednostkowy jest często pisany jako $e ^ {T-T ^ \dagger} $, gdzie $T-T ^ \dagger $ jest operatorem klastra hermitian.</span><span class="sxs-lookup"><span data-stu-id="5a800-127">This unitary operator is commonly written as $e^{T-T^\dagger}$, where $T-T^\dagger$ is the anti-Hermitian cluster operator.</span></span> <span data-ttu-id="5a800-128">W tym celu \begin{align} \ket{\ psi_ {\RM {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.</span><span class="sxs-lookup"><span data-stu-id="5a800-128">Thus \begin{align} \ket{\psi_{\rm {UCC}}} = e^{T-T^\dagger}\ket{\psi_{\rm{SCF}}}.</span></span>
<span data-ttu-id="5a800-129">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5a800-129">\end{align}</span></span>

<span data-ttu-id="5a800-130">Często należy również podzielić operator klastra $T = T_1 + T_2 + \cdots $ na części, gdzie każda część $T _j $ zawiera $j $-terms.</span><span class="sxs-lookup"><span data-stu-id="5a800-130">It is also common to split the cluster operator $T = T_1 + T_2 + \cdots$ into parts, where each part $T_j$ contains $j$-body terms.</span></span> <span data-ttu-id="5a800-131">Ogólnie rzecz biorąc, teoretycznie sprzężone klaster, operator jednoczęściowego klastra (zmiennoprzecinkowych) ma postać \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}</span><span class="sxs-lookup"><span data-stu-id="5a800-131">In generalized coupled-cluster theory, the one-body cluster operator (singles) is of the form \begin{align} T_1 = \sum_{pq}t^{p}_{q} a^\dagger_p a_q, \end{align}</span></span>

<span data-ttu-id="5a800-132">i operator dwuczęściowego klastra (podwaja) ma postać \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {RS} a ^ \ dagger_p ^ \ dagger_q a_r a_s.</span><span class="sxs-lookup"><span data-stu-id="5a800-132">and two-body cluster operator (doubles) is of the form \begin{align} T_2 = \sum_{pqrs}t^{pq}_{rs} a^\dagger_p a^\dagger_q a_r a_s.</span></span>
<span data-ttu-id="5a800-133">\end{align}</span><span class="sxs-lookup"><span data-stu-id="5a800-133">\end{align}</span></span>

<span data-ttu-id="5a800-134">Warunki wyższej kolejności (potrójne, czterokrotne itp.) są możliwe, ale nie są obecnie obsługiwane przez bibliotekę chemii.</span><span class="sxs-lookup"><span data-stu-id="5a800-134">Higher-order terms (triples, quadruples, etc.) are possible, but not currently supported by the chemistry library.</span></span>

<span data-ttu-id="5a800-135">Na przykład, niech $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} $, i pozwól $T = 0,123 a ^ \ dagger_0 A_1 dagger_0a + 0,456 0,789 a ^ \ dagger_3 ^ \ A_1 a_2</span><span class="sxs-lookup"><span data-stu-id="5a800-135">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_1 a^\dagger_2\ket{0}$, and let $T= 0.123 a^\dagger_0 a_1 + 0.456 a^\dagger_0a^\dagger_3 a_1 a_2 - 0.789 a^\dagger_3a^\dagger_2 a_1 a_0$.</span></span> <span data-ttu-id="5a800-136">Następnie ten stan jest tworzona w bibliotece chemicznej w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="5a800-136">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { 1, 2 };

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {0, 1}, 0.123),
    (new [] {0, 3, 1, 2}, 0.456),
    (new [] {3, 2, 1, 0}, 0.789)
};

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunction = new FermionWavefunction<int>(reference, clusterOperator);
```

<span data-ttu-id="5a800-137">Convervationa pokrętła może być jawnie określana jako `SpinOrbital` zmienna zamiast indeksów całkowitych.</span><span class="sxs-lookup"><span data-stu-id="5a800-137">Spin convervation may be made explicit by instead specifying `SpinOrbital` indices instead of integer indices.</span></span> <span data-ttu-id="5a800-138">Na przykład niech $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} ^ \ dagger_ {2, \downarrow}\ket {0} $ i let $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ to pokrętło convserving.</span><span class="sxs-lookup"><span data-stu-id="5a800-138">For example, let $\ket{\psi_{\rm{SCF}}} = a^\dagger_{1,\uparrow} a^\dagger_{2, \downarrow}\ket{0}$, and let $T= 0.123 a^\dagger_{0, \uparrow} a_{1, \uparrow} + 0.456 a^\dagger_{0, \uparrow} a^\dagger_{3, \downarrow} a_{1, \uparrow} a_{2, \downarrow} - 0.789 a^\dagger_{3,\uparrow} a^\dagger_{2,\uparrow} a_{1,\uparrow} a_{0, \uparrow}$ be spin convserving.</span></span> <span data-ttu-id="5a800-139">Następnie ten stan jest tworzona w bibliotece chemicznej w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="5a800-139">Then this state is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Create a list describing the cluster operator
// The first half of each list of integers will be
// associated with the creation operators, and
// the second half with the annihilation operators.
var clusterOperator = new[]
{
    (new [] {(0, Spin.u), (1, Spin.u)}, 0.123),
    (new [] {(0, Spin.u), (3, Spin.d), (1, Spin.u), (2, Spin.d)}, 0.456),
    (new [] {(3, Spin.u), (2, Spin.u), (1, Spin.u), (0, Spin.u)}, 0.789)
}.Select(o => (o.Item1.ToSpinOrbitals(), o.Item2);

// Create a fermion wavefunction object that represents the 
// unitary coupled-cluster wavefunction. It is assumed implicity
// that the exponent of the unitary coupled-cluster operator
// is the cluster operator minus its Hermitian conjugate.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(reference, clusterOperator);

// Convert the wavefunction indexed by spin-orbitals to one indexed
// by integers
var wavefunctionInteger = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="5a800-140">Udostępniamy również wygodną funkcję, która wylicza wszystkie operatory klastrów z odwracaniem, które annihilate tylko zajęte orbitals i wciągaj tylko do niezajętego orbitals.</span><span class="sxs-lookup"><span data-stu-id="5a800-140">We also provide a convenience function that enumerates over all spin-conversing cluster operators that annihilate only occupied spin-orbitals and excite to only unoccupied spin-orbitals.</span></span>
```csharp
// Create a list of indices of the creation operators
// for the single-reference state
var reference = new[] { (1, Spin.u), (2, Spin.d) }.ToSpinOrbitals();

// Generate all spin-conversing excitations from spin-orbitals 
// occupied by the reference state to virtual orbitals.
var generatedExcitations = reference.CreateAllUCCSDSingletExcitations(nOrbitals: 3).Excitations;

// This is the list of expected spin-consvering excitations
var expectedExcitations = new[]
{
    new []{ (0, Spin.u), (1,Spin.u)},
    new []{ (2, Spin.u), (1,Spin.u)},
    new []{ (0, Spin.d), (2,Spin.d)},
    new []{ (1, Spin.d), (2,Spin.d)},
    new []{ (0, Spin.u), (0, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.u), (1, Spin.d), (2, Spin.d), (1,Spin.u)},
    new []{ (0, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)},
    new []{ (1, Spin.d), (2, Spin.u), (2, Spin.d), (1,Spin.u)}
}.Select(o => new IndexOrderedSequence<SpinOrbital>(o.ToLadderSequence()));

// The following two assertions are true, and verify that the generated 
// excitations exactly match the expected excitations.
var bool0 = generatedExcitations.Keys.All(expectedExcitations.Contains);
var bool1 = generatedExcitations.Count() == expectedExcitations.Count();
```
