---
title: Symmetries całk molekularnych | Microsoft Docs
description: Symmetries ze koncepcyjną dokumentacją cząsteczkową
author: nathanwiebe2
ms.author: nawiebe
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.symmetries
ms.openlocfilehash: 041d600bc8d65e7d67f5fe7d61a69426fb42ffbc
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442383"
---
# <a name="symmetries-of-molecular-integrals"></a><span data-ttu-id="d3ee7-103">Symmetries całk molekularnych</span><span class="sxs-lookup"><span data-stu-id="d3ee7-103">Symmetries of Molecular Integrals</span></span>

<span data-ttu-id="d3ee7-104">Podstawą symetrii Coulomb — hamiltonian, która jest hamiltonian podaną w [modelach Quantum dla systemów elektronicznych](xref:microsoft.quantum.chemistry.concepts.quantummodels), która opisuje Electrons, ze sobą współdziałanie elektrycznie i z jądrem, prowadzi do kilku symmetries, które mogą być wykorzystane do skompresowania warunków w hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-104">The inherent symmetry of the Coulomb Hamiltonian, which is the Hamiltonian given in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels), that describes electrons interacting electrically with each other and with the nuclei, leads to a number of symmetries that can be exploited to compress the terms in the Hamiltonian.</span></span>
<span data-ttu-id="d3ee7-105">Ogólnie rzecz biorąc, jeśli nie zostaną wykonane żadne dalsze założenia dotyczące funkcji podstawy $ \psi_j $, mamy tylko, że \begin{Equation} H_ {pqrs} = H_ {qpsr}, \tag{★} \label{EQ: hpqrs} \end{Equation}, które mogą być od siebie od całek w [modelach Quantum dla Systemy elektroniczne](xref:microsoft.quantum.chemistry.concepts.quantummodels) z uwzględnieniem, że ich wartości pozostają takie same, jeśli $p, q $ i $r, s $ są zamiennie zmieniane z ochrony.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-105">In general if no further assumptions are made about the basis functions $\psi_j$ then we only have that \begin{equation} h_{pqrs}= h_{qpsr},\tag{★}\label{eq:hpqrs} \end{equation} which can be immediately seen from the integrals in [Quantum Models for Electronic Systems](xref:microsoft.quantum.chemistry.concepts.quantummodels) upon noting that their values remain identical if $p,q$ and $r,s$ are interchanged from anti-commutation.</span></span>

<span data-ttu-id="d3ee7-106">Jeśli założono, że orbitals jest prawdziwe (jak w przypadku podstaw dwukierunkowych), możemy jeszcze \begin{Equation} H_ {pqrs} = H_ {qpsr} = H_ {srqp} = H_ {rspq} = H_ {rqps} = H_ {psrq} = H_ {} SPQR {★} H_: qrsp} .\tag równanie} uwzględniając takie założenia, można użyć powyższej symmetries, aby zmniejszyć ilość danych potrzebnych do przechowywania elementów macierzy hamiltonian przez współczynnik $8 $; Chociaż taka metoda sprawia, że importowanie danych jest w spójny sposób nieco trudniejsze.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-106">If we assume that the spin-orbitals are real-valued (as they are for Gaussian orbital bases) then we further have that \begin{equation} h_{pqrs} = h_{qpsr} = h_{srqp} = h_{rspq}=h_{rqps}=h_{psrq}=h_{spqr}=h_{qrsp}.\tag{★}\label{eq:hpqrsreal} \end{equation} Given such assumptions hold, we can use the above symmetries to reduce the data needed to store the matrix elements of the Hamiltonian by a factor of $8$; although doing so makes importing data in a consistent way slightly more challenging.</span></span>
<span data-ttu-id="d3ee7-107">Na szczęście Biblioteka symulacji hamiltonian ma podprocedury, których można użyć do zaimportowania plików całkowitych z [LIQUI $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) lub bezpośrednio z poziomu [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span><span class="sxs-lookup"><span data-stu-id="d3ee7-107">Fortunately the Hamiltonian simulation library has subroutines that can be used to import integral files from either [LIQUI$|\rangle$](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) or directly from [NWChem](http://www.nwchem-sw.org/index.php/Main_Page).</span></span>

<span data-ttu-id="d3ee7-108">Dwuczęściowe całki molekularne (tj. $h\_{pq} $ i $h\_{pqrs} $ terms), takich jak te, są reprezentowane przy użyciu typu `OrbitalIntegral`, który zapewnia wiele przydatnych funkcji do wyrażania tego symetrii.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-108">Molecular orbital integrals (i.e. the $h\_{pq}$ and $h\_{pqrs}$ terms) such as these are represented using the `OrbitalIntegral` type, which provides a number of helpful functions to express this symmetry.</span></span>
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

<span data-ttu-id="d3ee7-109">Oprócz wyliczania wszystkich całkowitych częściowych, które są identycznie takie same, lista wszystkich indeksów kręgowych zawartych w hamiltonian reprezentowanej przez `OrbitalIntegral` może być generowana w następujący sposób.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-109">In addition to enumerating over all orbital integrals that are numerically identical, a list of all spin-orbital indices contained in the Hamiltonian represented by an `OrbitalIntegral` may be generated as follows.</span></span>
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a><span data-ttu-id="d3ee7-110">Konstruowanie Fermionic Hamiltonians z całk molekularnych</span><span class="sxs-lookup"><span data-stu-id="d3ee7-110">Constructing Fermionic Hamiltonians from Molecular Integrals</span></span>

<span data-ttu-id="d3ee7-111">Zamiast konstruowania Fermionic hamiltonian przez dodanie `FermionTerm`s, wszystkie warunki odpowiadające każdej liczbie całkowitej mogą zostać dodane automatycznie.</span><span class="sxs-lookup"><span data-stu-id="d3ee7-111">Rather than constructing a Fermionic Hamiltonian by adding `FermionTerm`s, all terms corresponding to each orbital integral may be added automatically.</span></span>
<span data-ttu-id="d3ee7-112">Na przykład poniższy kod automatycznie wylicza wszystkie permutacje symmetries i porządkuje warunki w kolejności kanonicznej:</span><span class="sxs-lookup"><span data-stu-id="d3ee7-112">For example, the following code automatically enumerates over all permutational symmetries and orders the terms in canonical order:</span></span> 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
