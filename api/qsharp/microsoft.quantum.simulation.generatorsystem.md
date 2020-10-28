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
# <a name="generatorsystem-user-defined-type"></a><span data-ttu-id="33de5-102">GeneratorSystem typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="33de5-102">GeneratorSystem user defined type</span></span>

<span data-ttu-id="33de5-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="33de5-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="33de5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="33de5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="33de5-105">Reprezentuje kolekcję `GeneratorIndex` es.</span><span class="sxs-lookup"><span data-stu-id="33de5-105">Represents a collection of `GeneratorIndex`es.</span></span>

<span data-ttu-id="33de5-106">Wykonujemy iterację tej kolekcji przy użyciu jednego indeksu Integer, a rozmiar kolekcji jest uznawany za znany.</span><span class="sxs-lookup"><span data-stu-id="33de5-106">We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.</span></span>

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a><span data-ttu-id="33de5-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="33de5-107">Remarks</span></span>

<span data-ttu-id="33de5-108">Wystąpienia `GeneratorSystem` można definiować łatwo przy użyciu <xref:microsoft.quantum.arrays.lookupfunction> funkcji.</span><span class="sxs-lookup"><span data-stu-id="33de5-108">Instances of `GeneratorSystem` can be defined easily using the <xref:microsoft.quantum.arrays.lookupfunction> function.</span></span>

## <a name="see-also"></a><span data-ttu-id="33de5-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="33de5-109">See Also</span></span>

- [<span data-ttu-id="33de5-110">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="33de5-110">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)