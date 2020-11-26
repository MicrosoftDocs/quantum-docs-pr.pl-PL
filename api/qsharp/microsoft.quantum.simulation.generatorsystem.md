---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: GeneratorSystem typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225231"
---
# <a name="generatorsystem-user-defined-type"></a>GeneratorSystem typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje kolekcję `GeneratorIndex` es.

Wykonujemy iterację tej kolekcji przy użyciu jednego indeksu Integer, a rozmiar kolekcji jest uznawany za znany.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Uwagi

Wystąpienia `GeneratorSystem` można definiować łatwo przy użyciu <xref:microsoft.quantum.arrays.lookupfunction> funkcji.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)