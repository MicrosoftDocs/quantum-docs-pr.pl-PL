---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718752"
---
# <a name="where-function"></a><span data-ttu-id="353d4-102">WHERE — funkcja</span><span class="sxs-lookup"><span data-stu-id="353d4-102">Where function</span></span>

<span data-ttu-id="353d4-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="353d4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="353d4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="353d4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="353d4-105">Podano predykat i tablicę, zwraca indeksy tej tablicy, w której predykat ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="353d4-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="353d4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="353d4-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="353d4-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="353d4-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="353d4-108">Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.</span><span class="sxs-lookup"><span data-stu-id="353d4-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="353d4-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="353d4-109">array : 'T[]</span></span>

<span data-ttu-id="353d4-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="353d4-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="353d4-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="353d4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="353d4-112">Tablica indeksów, gdzie `predicate` ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="353d4-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="353d4-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="353d4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="353d4-114">'C</span><span class="sxs-lookup"><span data-stu-id="353d4-114">'T</span></span>

<span data-ttu-id="353d4-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="353d4-115">The type of `array` elements.</span></span>