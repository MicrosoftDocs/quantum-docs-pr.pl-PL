---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 8d36f74fbf122469e9e829b950e4ed9a6e3a35a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723902"
---
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Reprezentuje pojedynczy termin pierwotny w zestawie wszystkich generatorów dynamicznych, np. operatorów hermitian, dla których istnieje mapa z tego generatora do czasu ewolucji przez ten generator, za pośrednictwem `EvolutionSet` .

Pierwszy element (int [], Double []) jest indeksem, który jest pojedynczym terminem — na przykład Pauli ciąg XXY z współczynnikem 0,5 będzie indeksowany przez ([1, 1, 2], [0,5]). Alternatywnie, Hamiltonians sparametryzowane przez zmienną ciągłą, taką jak X cos φ + Y Sin φ, może być reprezentowane przez ([], [φ]). Drugi element indeksuje podsystem, na którym działa Generator.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>Uwagi

> [!WARNING]
> Interpretacja elementu `GeneratorIndex` nie jest zdefiniowana, z wyjątkiem odwołania do określonego zestawu generatorów.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Symulacja. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. Quantum. Symulacja. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)