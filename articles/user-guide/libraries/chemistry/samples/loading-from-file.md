---
title: Ładowanie operatora Hamiltona z pliku
description: Dowiedz się, jak automatycznie generować duże hamiltonian przy użyciu schematu Broombridge.
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: sample
uid: microsoft.quantum.chemistry.examples.loadhamiltonian
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4bd663ade7649be05058f07bee1acf541ec3e487
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844114"
---
# <a name="loading-a-hamiltonian-from-file"></a>Ładowanie operatora Hamiltona z pliku
Wcześniej tworzymy Hamiltonians przez dodanie do niej poszczególnych warunków. Chociaż jest to bardzo szczegółowe w przypadku małych przykładów, Chemia Quantum na skalę wymaga Hamiltonians z milionami lub miliardami warunków. Takie Hamiltonians, generowane przez pakiety chemii, takie jak NWChem, są zbyt duże, aby można je było zaimportować. W tym przykładzie pokazano, jak `FermionHamiltonian` wystąpienie może być automatycznie generowane na podstawie cząsteczki reprezentowanej przez [schemat Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge). W przypadku elementu Reference można przeprowadzić inspekcję podanego `LithiumHydrideGUI` przykładu lub `RunSimulation` próbki. Ograniczona pomoc techniczna jest również dostępna do zaimportowania w formacie użytym przez [LIQUi |>](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/).

Rozważmy przykładową cząsteczkę azotu, która znajduje się w `IntegralData/YAML` folderze repozytorium przykładów. Metoda ładowania `Broombridge` schematu jest prosta.

```csharp
// This is the name of the file we want to load
var filename = @"n2_1_00Re_sto3g.nw.out.yaml";
// This is the directory containing the file
var root = @"IntegralData\YAML";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge($@"{root}\{filename}");

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.First()`, which selects the first element of the list.
var problem = broombridge.ProblemDescriptions.First();

// This extracts the `OrbitalIntegralHamiltonian` from Broombridge format,
// then converts it to a fermion Hamiltonian, then to a Jordan-Wigner
// representation.
var orbitalIntegralHamiltonian = problem.OrbitalIntegralHamiltonian;
var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);
var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(Pauli.QubitEncoding.JordanWigner);
```

Schemat Broombridge zawiera również sugestie dotyczące stanu początkowego do przygotowania. Etykiety, np. `"|G⟩"` lub `"|E1⟩"` , dla tych stanów mogą być widoczne przez sprawdzenie pliku. W celu przygotowania tych początkowych Stanów `qSharpData` zużyte przez Q# algorytmy Quantum są uzyskiwane podobnie jak w [poprzedniej sekcji](xref:microsoft.quantum.chemistry.examples.energyestimate), ale z dodatkowym parametrem, wybierając żądany stan początkowy. Na przykład
```csharp
// The desired initial state, assuming that a description of it is present in the
// Broombridge schema.
var state = "|E1>";
var wavefunction = problem.Wavefunctions[state].ToIndexing(IndexConvention.UpDown);

// This creates the qSharpData consumable by the Q# chemistry library algorithms.
var qSharpHamiltonianData = jordanWignerEncoding.ToQSharpFormat();
var qSharpWavefunctionData = wavefunction.ToQSharpFormat();
var qSharpData = QSharpFormat.Convert.ToQSharpFormat(qSharpHamiltonianData, qSharpWavefunctionData);
```

Wszystkie powyższe kroki mogą być skracane przy użyciu podanych metod dogodnych w następujący sposób.
```csharp
// This is the name of the file we want to load
var filename = "...";

// This deserializes a Broombridge file, given its filename.
var broombridge = Broombridge.Deserializers.DeserializeBroombridge(filename);

// Note that the deserializer returns a list of `ProblemDescription` instances 
// as the file might describe multiple Hamiltonians. In this example, there is 
// only one Hamiltonian. So we use `.Single()`, which selects the only element of the list.
var problem = broombridge.ProblemDescriptions.Single();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
// If no state is specified, the Hartree-Fock state is used by default.
var qSharpData = problem.ToQSharpFormat("|E1>");
```

Możemy również załadować hamiltonian z LIQUi |> format, przy użyciu bardzo podobnej składni. 

```csharp
// This is the name of the file we want to load
var filename = @"fe2s2_sto3g.dat"; // This is Ferrodoxin.
// This is the directory containing the file
var root = @"IntegralData\Liquid";

// Deserialize the LiQuiD format.
var problem = LiQuiD.Deserialize($@"{root}\{filename}").First();

// This is a data structure representing the Jordan-Wigner encoding 
// of the Hamiltonian that we may pass to a Q# algorithm.
var qSharpData = problem.ToQSharpFormat();
```

Wykonując ten proces z dowolnego wystąpienia Broombridge lub dowolnego etapu pośredniego, algorytmy Quantum, takie jak oszacowanie fazy Quantum, można uruchomić na określonym problemie struktury elektronicznej.
