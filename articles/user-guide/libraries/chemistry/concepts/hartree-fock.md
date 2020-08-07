---
title: Hartree-Fock teoretyczne
description: Dowiedz się więcej o teorii Hartree – Fock, prosty sposób konstruowania stanu początkowego dla systemów Quantum.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2d5e597c36f7873dfd1e011e7ce7d4b01c0f786e
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869548"
---
# <a name="hartreefock-theory"></a>Hartree — teoretycznie Fock

Prawdopodobnie największą istotną ilością w symulacji chemicznej Quantum jest stan ziemi, czyli minimalny eigenvector energii macierzy hamiltonian.
Wynika to z faktu, że w przypadku większości cząsteczek w ilościach temperatury pokojowej, takich jak stawki reakcji, są narzucane przez wolne różnice energii między Stanami Quantum, które opisują początek i koniec kroku w zakresie reakcji i temperatury pokojowej, w przypadku których stan pośredni to zwykle Stany terenowe.
Stan ziemi jest zazwyczaj zbyt trudny do uczenia (nawet w przypadku komputera z systemem Quantum), ponieważ jest to dystrybucja na dużą liczbę konfiguracji.
Można poznać ilości, takie jak energia stanu ziemi.
Na przykład jeśli $ \ket{\psi} $ jest dowolnym czystym stanem Quantum, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} zapewnia średnią energię, którą system ma w tym stanie.
Stan ziemi to stan, który zapewnia najmniejszą taką wartość. Z tego powodu wybór stanu, który jest możliwie zbliżony do rzeczywistego stanu ziemi, jest istotnie istotny do oszacowania energii bezpośrednio (jak jest to wykonywane w odniesieniu do odmiany eigensolvers) lub przez oszacowanie fazy.

Hartree — teoretycznie Fock zapewnia prosty sposób konstruowania stanu początkowego dla systemów Quantum. Powoduje to przekazanie jednego Slaterego wyznacznika do stanu uziemienia systemu Quantum. W tym celu znajduje obrót w przestrzeni Fock, który minimalizuje energię stanu ziemi. W szczególności dla systemu $N $ Electrons Metoda wykonuje obrót \begin{Equation} \ prod_ {j = 0} ^ {N-1} a ^ \ dagger_j \ket {0} \mapsto \ prod_ {j = 0} ^ {N-1} e ^ {u} a ^ \ dagger_j e ^ {-u} \ket {0} \defeq\ prod_ {j = 0} ^ {N-1} \widetilde{a} ^ \ dagger_j \ket {0} , \end{Equation} z antyą hermitian (tj. $u =-u ^ \dagger $) Matrix $u = \ sum_ {pq} U_ {pq} a ^ \ dagger_p a_q $. Należy zauważyć, że macierz $u $ reprezentuje rotacje obrotowe i $ \widetilde{a} ^ \ dagger_j $ i $ \widetilde{a} _j $ przedstawia operatory tworzenia i Annihilation dla Electrons zajmują Hartree — Fock molekularny-orbitals.


Macierz $u $ jest następnie zoptymalizowana pod kątem zminimalizowania oczekiwanej wartości energetycznej $ \bra {0} \ prod_ {j = 0} ^ {n-1} \widetilde{a} \_ j H \prod \_ {k = 0} ^ {n-1} \widetilde{a} ^ \ dagger_k \ket {0} $. Chociaż te problemy z optymalizacją mogą być ogólnie trudne, w ramach algorytmu Hartree – Fock, aby szybko przeprowadzić zbieżność z niemal optymalnym rozwiązaniem dla problemu optymalizacji, szczególnie w przypadku cząsteczek z powłoką zamkniętą w geometrie równowagi. Możemy określić te Stany jako wystąpienie `FermionWavefunction` obiektu. Na przykład stan $a ^ \ dagger_ {1} ^ \ dagger_ {2} ^ \ dagger_ {6} \ket {0} $ jest wystąpieniem w bibliotece chemii w następujący sposób.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Istnieje również możliwość indeksowania funkcji Wave przy użyciu `SpinOrbital` indeksów, a następnie przekonwertowania tych indeksów na liczby całkowite w następujący sposób.
```csharp
// Create a list of spin orbital indices of the creation operators
var indices = new[] { (0, Spin.d), (1,Spin.u), (3, Spin.u) };

// Convert the list of indices to a `FermionWavefunction` object.
var wavefunctionSpinOrbital = new FermionWavefunction<SpinOrbital>(indices.ToSpinOrbitals());

// Convert a wavefunction indexed by spin orbitals to
// one indexed by integers
var wavefunctionInt = wavefunctionSpinOrbital.ToIndexing(IndexConvention.UpDown);
```

Najbardziej z największą cechą dotyczącą Hartree — Fock jest to, że daje ona stan Quantum, który nie Entanglement między Electrons.
Oznacza to, że często zapewnia to odpowiedni jakościowy opis właściwości systemów molekularnych. 

Stan Hartree-Fock może być również odtworzony z programu w `FermionHamiltonian` następujący sposób.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Jednak uzyskanie dokładnych wyników, szczególnie w przypadku silnie skorelowanych systemów, wymaga, aby Stany Quantum wykraczające poza Hartree — Fock.
