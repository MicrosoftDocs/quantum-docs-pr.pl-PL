---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724560"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Reprezentuje kolekcję `GeneratorIndex` es.

Wykonujemy iterację tej kolekcji przy użyciu jednego indeksu Integer, a rozmiar kolekcji jest uznawany za znany.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Uwagi

Wystąpienia `GeneratorSystem` można definiować łatwo przy użyciu <xref:microsoft.quantum.arrays.lookupfunction> funkcji.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)