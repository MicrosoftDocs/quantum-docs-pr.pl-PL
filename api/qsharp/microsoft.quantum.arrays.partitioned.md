---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Podzielona funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220505"
---
# <a name="partitioned-function"></a><span data-ttu-id="793f3-102">Podzielona funkcja</span><span class="sxs-lookup"><span data-stu-id="793f3-102">Partitioned function</span></span>

<span data-ttu-id="793f3-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="793f3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="793f3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="793f3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="793f3-105">Dzieli tablicę na wiele części.</span><span class="sxs-lookup"><span data-stu-id="793f3-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="793f3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="793f3-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="793f3-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="793f3-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="793f3-108">Liczba elementów w każdej części tablicy</span><span class="sxs-lookup"><span data-stu-id="793f3-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="793f3-109">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="793f3-109">arr : 'T[]</span></span>

<span data-ttu-id="793f3-110">Tablica wejściowa do podzielenia.</span><span class="sxs-lookup"><span data-stu-id="793f3-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="793f3-111">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="793f3-111">Output : 'T[][]</span></span>

<span data-ttu-id="793f3-112">Wiele tablic, w których pierwsza jest pierwsza tablica `nElements[0]` `arr` i druga tablica jest następną `nElements[1]` z `arr` itd. Ostatnia tablica będzie zawierać wszystkie pozostałe elementy.</span><span class="sxs-lookup"><span data-stu-id="793f3-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="793f3-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="793f3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="793f3-114">'C</span><span class="sxs-lookup"><span data-stu-id="793f3-114">'T</span></span>

