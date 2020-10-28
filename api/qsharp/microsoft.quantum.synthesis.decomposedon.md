---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725218"
---
# <a name="decomposedon-function"></a><span data-ttu-id="9feff-102">DecomposedOn, funkcja</span><span class="sxs-lookup"><span data-stu-id="9feff-102">DecomposedOn function</span></span>

<span data-ttu-id="9feff-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="9feff-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="9feff-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9feff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9feff-105">Dekomponowauje permutację na zmiennej</span><span class="sxs-lookup"><span data-stu-id="9feff-105">Decomposes a permutation on a variable</span></span>

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a><span data-ttu-id="9feff-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9feff-106">Description</span></span>

<span data-ttu-id="9feff-107">Nadana Permutacja $ \pi $ ( `perm` ) i indeks $i $ ( `index` ), ta metoda zwraca trzy Permutacje $ ((\ pi_l, \ pi_r), \pi ') $ w taki sposób, że obrazy $ \ pi_l $ i $ \ pi_r $ nie zmieniają bitów w ich elementach w indeksach innych niż $i $ i obrazy $ \pi ' $ nie zmieniają bitu $i $ w ich elementach.</span><span class="sxs-lookup"><span data-stu-id="9feff-107">Given a permutation $\pi$ (`perm`) and an index $i$ (`index`), this method returns three permutations $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>

## <a name="input"></a><span data-ttu-id="9feff-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9feff-108">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="9feff-109">uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9feff-109">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>




### <a name="index--int"></a><span data-ttu-id="9feff-110">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9feff-110">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--intintint"></a><span data-ttu-id="9feff-111">Wynik: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="9feff-111">Output : (([Int](xref:microsoft.quantum.lang-ref.int)[],[Int](xref:microsoft.quantum.lang-ref.int)[]),[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

