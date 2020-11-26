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
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="4d5d2-102">GeneratorSystem typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="4d5d2-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="4d5d2-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="4d5d2-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="4d5d2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d5d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d5d2-105">Reprezentuje kolekcję `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="4d5d2-106">Wykonujemy iterację tej kolekcji przy użyciu jednego indeksu Integer, a rozmiar kolekcji jest uznawany za znany.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="4d5d2-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4d5d2-107">Remarks</span></span>

<span data-ttu-id="4d5d2-108">Wystąpienia `GeneratorSystem` można definiować łatwo przy użyciu <xref:microsoft.quantum.arrays.lookupfunction> funkcji.</span><span class="sxs-lookup"><span data-stu-id="4d5d2-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="4d5d2-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4d5d2-109">See Also</span></span>

- [<span data-ttu-id="4d5d2-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="4d5d2-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)