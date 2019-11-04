---
title: Hartree-Fock teoretyczne | Microsoft Docs
description: Hartree — dokumenty teoretyczne
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.hartreefock
ms.openlocfilehash: e73111ae710e11ca6730581b8be711cf32783677
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184104"
---
# <a name="hartreefock-theory"></a>Hartree — teoretycznie Fock

Prawdopodobnie największą istotną ilością w symulacji chemicznej Quantum jest stan ziemi, czyli minimalny eigenvector energii macierzy hamiltonian.
Wynika to z faktu, że w przypadku większości cząsteczek w ilościach temperatury pokojowej, takich jak stawki reakcji, są narzucane przez wolne różnice energii między Stanami Quantum, które opisują początek i koniec kroku w ramach ścieżki reakcji i temperatury pokojowej. stanem są zwykle Stany terenowe.
Stan ziemi jest zazwyczaj zbyt trudny do uczenia (nawet w przypadku komputera z systemem Quantum), ponieważ jest to dystrybucja na dużą liczbę konfiguracji.
Można poznać ilości, takie jak energia stanu ziemi.
Na przykład jeśli $ \ket{\psi} $ jest dowolnym czystym stanem Quantum, \begin{Equation} E = \bra{\psi} \hat{H} \ket{\psi} \end{Equation} zapewnia średnią energię, którą system ma w tym stanie.
Stan ziemi to stan, który zapewnia najmniejszą taką wartość. Z tego powodu wybór stanu, który jest możliwie zbliżony do rzeczywistego stanu ziemi, jest istotnie istotny do oszacowania energii bezpośrednio (jak jest to wykonywane w odniesieniu do odmiany eigensolvers) lub przez oszacowanie fazy.

Hartree — teoretycznie Fock zapewnia prosty sposób konstruowania stanu początkowego dla systemów Quantum. Powoduje to przekazanie jednego Slaterego wyznacznika do stanu uziemienia systemu Quantum. W tym celu znajduje obrót w przestrzeni Fock, który minimalizuje energię stanu ziemi. W szczególności w przypadku systemu $N $ Electrons Metoda wykonuje obrót \begin{Equation} \prod_{j = 0} ^ {N-1} a ^ \dagger_j \ket{0} \mapsto \prod_{j = 0} ^ {N-1} e ^ {u} a ^ \dagger_j e ^ {-u} \ket{0}\defeq\prod_{j = 0} ^ {N-1} \widetilde{a} ^ \dagger _j \ket{0}, \end{Equation} za pomocą hermitian \dagger (tj. $u =-u ^ \sum_{PQ} $), $u U_ {pq} a ^ \dagger_p a_q $. Należy zauważyć, że macierz $u $ reprezentuje rotacje rotacyjne i $ \widetilde{a} ^ \dagger_j $ i $ \widetilde{a}_j $ przedstawiają operatory tworzenia i Annihilation dla Electrons zajmują Hartree — Fock cząsteczkowa-orbitals.


Macierz $u $ jest następnie zoptymalizowana pod kątem zminimalizowania oczekiwanej energii $ \bra{0} \prod_{j = 0} ^ {N-1} \widetilde{a}\_j H \prod\_{k = 0} ^ {N-1} \widetilde{a} ^ \dagger_k\ket{0}$. Chociaż te problemy z optymalizacją mogą być ogólnie trudne, w ramach algorytmu Hartree – Fock, aby szybko przeprowadzić zbieżność z niemal optymalnym rozwiązaniem dla problemu optymalizacji, szczególnie w przypadku cząsteczek z powłoką zamkniętą w geometrie równowagi. Możemy określić te Stany jako wystąpienie obiektu `FermionWavefunction`. Na przykład stan $a ^ \dagger_{1}^ \dagger_{2}^ \dagger_{6}\ket{0}$ jest tworzona w bibliotece chemii w następujący sposób.
```csharp
// Create a list of integer indices of the creation operators
var indices = new[] { 1, 2, 6 };

// Convert the list of indices to a `FermionWavefunction` object.
// In this case, the indices are integers, so we use the `int`
// type specialization.
var wavefunction = new FermionWavefunction<int>(indices);
```
Istnieje również możliwość indeksowania funkcji Wave przy użyciu indeksów `SpinOrbital`, a następnie przekonwertowania indeksów na liczby całkowite w następujący sposób.
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

Stan Hartree-Fock może być również odtworzony z `FermionHamiltonian` w następujący sposób.
```csharp
// We initialize a fermion Hamiltonian.
var fermionHamiltonian = new FermionHamiltonian();

// Create a Hartree-Fock state from the Hamiltonian 
// with, say, `4` occupied spin orbitals.
var wavefunction = fermionHamiltonian.CreateHartreeFockState(nElectrons: 4);
```

Jednak uzyskanie dokładnych wyników, szczególnie w przypadku silnie skorelowanych systemów, wymaga, aby Stany Quantum wykraczające poza Hartree — Fock.