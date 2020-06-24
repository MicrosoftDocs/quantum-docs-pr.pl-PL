---
title: Skorelowane funkcje falowe
description: Dowiedz się więcej na temat korelacji dynamicznych i niedynamicznych w wavefunctions przy użyciu biblioteki chemii Microsoft Quantum.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.multireference
ms.openlocfilehash: 005ef86382ca72969b06a4206cab01f3845718e2
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275910"
---
# <a name="correlated-wavefunctions"></a>Skorelowane funkcje falowe

W przypadku wielu systemów, szczególnie tych znajdujących się w sąsiedztwie równowagi, [Hartree – Fock](xref:microsoft.quantum.chemistry.concepts.hartreefock) teoretycznie zapewnia jakościowy opis właściwości molekularnych za pomocą jednoelementowego stanu odwołania. Jednak w celu osiągnięcia dokładności ilościowej należy również wziąć pod uwagę wpływ korelacji. 

W tym kontekście ważne jest dinstinguish między korelacją dynamiczną i niedynamiczną.
Dynamiczne korelacje powstają od tendencji Electrons do pozostania, takich jak z powodu międzyelektronicznego napędu. Ten efekt może być modelowany przez rozważenie excitations Electrons z stanu odwołania. Niedynamiczne korelacje powstają, gdy wavefunction jest zdominowany przez dwie lub więcej konfiguracji w kolejności zerowego, nawet w celu uzyskania tylko jakościowego opisu systemu.
To wymaga nadłożenia znaczników i jest przykładem wieloodwołaniaowej wavefunction.

Biblioteka chemii umożliwia określenie zerowego Order wavefunction dla problemu wieloreferencyjnego jako nadpozycji znaczników. To podejście, które dzwonimy do wavefunctions rozrzedzenia, jest skuteczne, gdy tylko kilka składników wystarcza do określenia nadpozycji. Biblioteka udostępnia również metodę, aby uwzględnić dynamiczne korelacje na jednym wyznaczniku, za pośrednictwem uogólnionego, połączonego z jednostką ansatz. Ponadto tworzy również obwodów Quantum, które generują te Stany na komputerze Quantum. Te Stany mogą być określone w [schemacie Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)i udostępniamy również funkcje ręcznego określania tych stanów za pomocą biblioteki chemicznej.

## <a name="sparse-multi-reference-wavefunction"></a>Rozrzedzony wavefunction wiele odwołań
Stan wieloodwołania $ \ket{\ psi_ {\RM {MCSCF}}} $ może być jawnie określony jako liniowa kombinacja $N $-elektron Slater determininants.
\begin{align} \ket{\ psi_ {\RM {MCSCF}}} \propto \ sum_ {i_1 < i_2 < \cdots < i_N} \ lambda_ {i_1, i_2, \cdots, i_N} a ^ \ dagger_ {i_1} a ^ \ dagger_ {i_2} \cdots {dagger_} \ket {0} .
\end{align} na przykład stan $ \propto (0,1 a ^ \ dagger_1a ^ \ dagger_2a ^ \ dagger_6-0,2 a ^ \ dagger_2a ^ \ dagger_1a ^ \ dagger_5) \ket {0} $ można określić w bibliotece chemii w następujący sposób.
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
Ta jawna reprezentacja składników położeniu jest skuteczna, gdy należy określić tylko kilka składników. Należy unikać używania tej reprezentacji, gdy wiele składników jest wymaganych do dokładnego przechwycenia żądanego stanu. Przyczyną tego jest koszt usługi w ramach obwodu Quantum, który przygotowuje ten stan na komputerze z systemem Quantum, co oznacza, że skaluje się co najmniej liniowo przy użyciu liczby składników podpozycji, a najwyżej jedna z nich jest równa jednej kombinacji amplitud.

## <a name="unitary-coupled-cluster-wavefunction"></a>Połączone z jednostką — wavefunction klastra
Istnieje również możliwość określenia jednostki powiązanej-Cluster wavefunction $ \ket{\ psi_ {\RM {UCC}}} $ przy użyciu biblioteki chemistery. W takiej sytuacji mamy jednoelementowy stan odwołania, powiedzmy, $ \ket{\ psi_ {\rm{SCF}}} $. Składniki połączonego z jednostką wavefunction klastra są następnie określone jako niejawne przez operatora jednostki działającej na stanie odwołania.
Ten operator jednostkowy jest często pisany jako $e ^ {T-T ^ \dagger} $, gdzie $T-T ^ \dagger $ jest operatorem klastra hermitian. W tym celu \begin{align} \ket{\ psi_ {\RM {UCC}}} = e ^ {T-T ^ \dagger}\ket{\ psi_ {\rm{SCF}}}.
\end{align}

Często należy również podzielić operator klastra $T = T_1 + T_2 + \cdots $ na części, gdzie każda część $T _j $ zawiera $j $-terms. Ogólnie rzecz biorąc, teoretycznie sprzężone klaster, operator jednoczęściowego klastra (zmiennoprzecinkowych) ma postać \begin{align} T_1 = \ sum_ {pq} T ^ {p} _ {q} a ^ \ dagger_p a_q, \end{align}

i operator dwuczęściowego klastra (podwaja) ma postać \begin{align} T_2 = \ sum_ {pqrs} T ^ {pq} _ {RS} a ^ \ dagger_p ^ \ dagger_q a_r a_s.
\end{align}

Warunki wyższej kolejności (potrójne, czterokrotne itp.) są możliwe, ale nie są obecnie obsługiwane przez bibliotekę chemii.

Na przykład, niech $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_1 ^ \ dagger_2 \ket {0} $, i pozwól $T = 0,123 a ^ \ dagger_0 A_1 dagger_0a + 0,456 0,789 a ^ \ dagger_3 ^ \ A_1 a_2 Następnie ten stan jest tworzona w bibliotece chemicznej w następujący sposób.
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

Convervationa pokrętła może być jawnie określana jako `SpinOrbital` zmienna zamiast indeksów całkowitych. Na przykład niech $ \ket{\ psi_ {\rm{SCF}}} = a ^ \ dagger_ {1, \uparrow} ^ \ dagger_ {2, \downarrow}\ket {0} $ i let $T = 0,123 a ^ \ dagger_ {0, \uparrow} a_ {1, \uparrow} + 0,456 a ^ \ dagger_ {0, \uparrow} a ^ \ dagger_ {3, \downarrow} a_ {1, \uparrow} a_ {2, \downarrow}-0,789 a ^ \ dagger_ {3, \uparrow} a ^ \ dagger_ {2, \uparrow} a_ {1, \uparrow} a_ {0, \uparrow} $ to pokrętło convserving. Następnie ten stan jest tworzona w bibliotece chemicznej w następujący sposób.
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

Udostępniamy również wygodną funkcję, która wylicza wszystkie operatory klastrów z odwracaniem, które annihilate tylko zajęte orbitals i wciągaj tylko do niezajętego orbitals.
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
