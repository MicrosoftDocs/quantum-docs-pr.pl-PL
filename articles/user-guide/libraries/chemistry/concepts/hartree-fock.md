---
title: Hartree-Fock teoretyczne
description: Dowiedz się więcej o teorii Hartree – Fock, prosty sposób konstruowania stanu początkowego dla systemów Quantum.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: 6fa63cbe13fe98565ffb42b56f3ade86720cedb3
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275946"
---
# <a name="hartreefock-theory"></a><span data-ttu-id="ab005-103">Hartree — teoretycznie Fock</span><span class="sxs-lookup"><span data-stu-id="ab005-103">Hartree–Fock Theory</span></span>

<span data-ttu-id="ab005-104">Prawdopodobnie największą istotną ilością w symulacji chemicznej Quantum jest stan ziemi, czyli minimalny eigenvector energii macierzy hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="ab005-104">Perhaps the most important quantity in quantum chemistry simulation is the ground state, which is the minimum energy eigenvector of the Hamiltonian matrix.</span></span>
<span data-ttu-id="ab005-105">Wynika to z faktu, że w przypadku większości cząsteczek w ilościach temperatury pokojowej, takich jak stawki reakcji, są narzucane przez wolne różnice energii między Stanami Quantum, które opisują początek i koniec kroku w zakresie reakcji i temperatury pokojowej, w przypadku których stan pośredni to zwykle Stany terenowe.</span><span class="sxs-lookup"><span data-stu-id="ab005-105">This is because for most molecules at room temperature quantities such as reaction rates are dominated by free energy differences between quantum states that describe the beginning and end of a step in a reaction pathway and at room temperature such intermediate state are usually ground states.</span></span>
<span data-ttu-id="ab005-106">Stan ziemi jest zazwyczaj zbyt trudny do uczenia (nawet w przypadku komputera z systemem Quantum), ponieważ jest to dystrybucja na dużą liczbę konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ab005-106">While the ground state is typically too hard to learn (even with a quantum computer) because it is a distribution over an exponentially large number of configurations.</span></span>
<span data-ttu-id="ab005-107">Można poznać ilości, takie jak energia stanu ziemi.</span><span class="sxs-lookup"><span data-stu-id="ab005-107">Quantities such as ground state energy can be learned.</span></span>
<span data-ttu-id="ab005-108">Na przykład jeśli $ \ket{\psi} $ jest dowolnym czystym stanem Quantum, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} zapewnia średnią energię, którą system ma w tym stanie.</span><span class="sxs-lookup"><span data-stu-id="ab005-108">For example, if $\ket{\psi}$ is any pure quantum state then \begin{equation} E = \bra{ \psi } \hat{H} \ket{\psi} \end{equation} gives the mean energy that the system has in that state.</span></span>
<span data-ttu-id="ab005-109">Stan ziemi to stan, który zapewnia najmniejszą taką wartość.</span><span class="sxs-lookup"><span data-stu-id="ab005-109">The ground state then is the state that gives the smallest such value.</span></span> <span data-ttu-id="ab005-110">Z tego powodu wybór stanu, który jest możliwie zbliżony do rzeczywistego stanu ziemi, jest istotnie istotny do oszacowania energii bezpośrednio (jak jest to wykonywane w odniesieniu do odmiany eigensolvers) lub przez oszacowanie fazy.</span><span class="sxs-lookup"><span data-stu-id="ab005-110">As a result, choosing a state that is as close as possible to the true ground state is vitally important for estimating the energy either directly (as is done in variational eigensolvers) or through phase estimation.</span></span>

<span data-ttu-id="ab005-111">Hartree — teoretycznie Fock zapewnia prosty sposób konstruowania stanu początkowego dla systemów Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab005-111">Hartree–Fock theory gives a simple way to construct the initial state for quantum systems.</span></span> <span data-ttu-id="ab005-112">Powoduje to przekazanie jednego Slaterego wyznacznika do stanu uziemienia systemu Quantum.</span><span class="sxs-lookup"><span data-stu-id="ab005-112">It yields a single Slater-determinant approximation to the ground state of a quantum system.</span></span> <span data-ttu-id="ab005-113">W tym celu znajduje obrót w przestrzeni Fock, który minimalizuje energię stanu ziemi.</span><span class="sxs-lookup"><span data-stu-id="ab005-113">To that end, it finds a rotation within Fock-space that minimizes the ground state energy.</span></span> <span data-ttu-id="ab005-114">W szczególności dla systemu $N $ Electrons Metoda wykonuje obrót \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} z antyą hermitian (tj. $u =-u ^ \dagger $) Matrix $u = \ sum_ {pq} U_ {pq} a ^ \ dagger_p a_q $.</span><span class="sxs-lookup"><span data-stu-id="ab005-114">In particular, for a system of $N$ electrons the method performs the rotation \begin{equation} \prod_{j=0}^{N-1} a^\dagger_j \ket{0} \mapsto \prod_{j=0}^{N-1} e^{u} a^\dagger_j e^{-u} \ket{0}\defeq\prod_{j=0}^{N-1}  \widetilde{a}^\dagger_j  \ket{0}, \end{equation} with an anti-Hermitian (i.e. $u= -u^\dagger$) matrix $u = \sum_{pq} u_{pq} a^\dagger_p a_q$.</span></span> <span data-ttu-id="ab005-115">Należy zauważyć, że macierz $u $ reprezentuje rotacje obrotowe i $ \widetilde{a} ^ \ dagger_j $ i $ \widetilde{a} _j $ przedstawia operatory tworzenia i Annihilation dla Electrons zajmują Hartree — Fock molekularny-orbitals.</span><span class="sxs-lookup"><span data-stu-id="ab005-115">It should be noted that the matrix $u$ represents the orbital rotations and $\widetilde{a}^\dagger_j$ and $\widetilde{a}_j$ represent creation and annihilation operators for electrons occupying Hartree–Fock molecular spin-orbitals.</span></span>


<span data-ttu-id="ab005-116">Macierz $u $ jest następnie zoptymalizowana pod kątem zminimalizowania oczekiwanej wartości energetycznej $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="ab005-116">The matrix $u$ is then optimized to minimize the expected energy $\bra{0} \prod_{j=0}^{N-1}  \widetilde{a}\_j  H \prod\_{k=0}^{N-1}  \widetilde{a}^\dagger_k\ket{0}$.</span></span> <span data-ttu-id="ab005-117">Chociaż te problemy z optymalizacją mogą być ogólnie trudne, w ramach algorytmu Hartree – Fock, aby szybko przeprowadzić zbieżność z niemal optymalnym rozwiązaniem dla problemu optymalizacji, szczególnie w przypadku cząsteczek z powłoką zamkniętą w geometrie równowagi.</span><span class="sxs-lookup"><span data-stu-id="ab005-117">While such optimization problems may be generically hard, in practice the Hartree–Fock algorithm tends to rapidly converge to a near-optimal solution to the optimization problem, especially for closed-shell molecules in the equilibrium geometries.</span></span> <span data-ttu-id="ab005-118">Możemy określić te Stany jako wystąpienie `FermionWavefunction` obiektu.</span><span class="sxs-lookup"><span data-stu-id="ab005-118">We may specify these states as an instance of the `FermionWavefunction` object.</span></span> <span data-ttu-id="ab005-119">Na przykład stan $a ^ \ dagger_ {1} ^ \ dagger_ {2} ^ \ dagger_ {6} \ket {0} $ jest wystąpieniem w bibliotece chemii w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="ab005-119">For instance, the state $a^\dagger_{1}a^\dagger_{2}a^\dagger_{6}\ket{0}$ is instantiated in the chemistry library as follows.</span></span>
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
<span data-ttu-id="ab005-120">Istnieje również możliwość indeksowania funkcji Wave przy użyciu `SpinOrbital` indeksów, a następnie przekonwertowania tych indeksów na liczby całkowite w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="ab005-120">It is also possible to index wave functions with `SpinOrbital` indices, and then convert these indices to integers as follows.</span></span>
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

<span data-ttu-id="ab005-121">Najbardziej z największą cechą dotyczącą Hartree — Fock jest to, że daje ona stan Quantum, który nie Entanglement między Electrons.</span><span class="sxs-lookup"><span data-stu-id="ab005-121">The most striking feature about Hartree–Fock theory is that it yields a quantum state that has no entanglement between the electrons.</span></span>
<span data-ttu-id="ab005-122">Oznacza to, że często zapewnia to odpowiedni jakościowy opis właściwości systemów molekularnych.</span><span class="sxs-lookup"><span data-stu-id="ab005-122">This means that it often provides a suitable qualitative description of properties of molecular systems.</span></span> 

<span data-ttu-id="ab005-123">Stan Hartree-Fock może być również odtworzony z programu w `FermionHamiltonian` następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="ab005-123">The Hartree-Fock state may also be reconstructed from a `FermionHamiltonian`  as follows.</span></span>
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

<span data-ttu-id="ab005-124">Jednak uzyskanie dokładnych wyników, szczególnie w przypadku silnie skorelowanych systemów, wymaga, aby Stany Quantum wykraczające poza Hartree — Fock.</span><span class="sxs-lookup"><span data-stu-id="ab005-124">However, obtaining accurate results, especially for strongly correlated systems, necessitate quantum states that go beyond Hartree–Fock theory.</span></span>
