---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Podzielona funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718977"
---
# <a name="partitioned-function"></a><span data-ttu-id="3962c-102">Podzielona funkcja</span><span class="sxs-lookup"><span data-stu-id="3962c-102">Partitioned function</span></span>

<span data-ttu-id="3962c-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3962c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3962c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3962c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3962c-105">Dzieli tablicę na wiele części.</span><span class="sxs-lookup"><span data-stu-id="3962c-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="3962c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3962c-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="3962c-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3962c-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3962c-108">Liczba elementów w każdej części tablicy</span><span class="sxs-lookup"><span data-stu-id="3962c-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="3962c-109">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="3962c-109">arr : 'T[]</span></span>

<span data-ttu-id="3962c-110">Tablica wejściowa do podzielenia.</span><span class="sxs-lookup"><span data-stu-id="3962c-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="3962c-111">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="3962c-111">Output : 'T[][]</span></span>

<span data-ttu-id="3962c-112">Wiele tablic, w których pierwsza jest pierwsza tablica `nElements[0]` `arr` i druga tablica jest następną `nElements[1]` z `arr` itd. Ostatnia tablica będzie zawierać wszystkie pozostałe elementy.</span><span class="sxs-lookup"><span data-stu-id="3962c-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3962c-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3962c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3962c-114">'C</span><span class="sxs-lookup"><span data-stu-id="3962c-114">'T</span></span>

