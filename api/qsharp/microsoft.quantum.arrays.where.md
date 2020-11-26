---
uid: Microsoft.Quantum.Arrays.Where
title: WHERE — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219927"
---
# <a name="where-function"></a><span data-ttu-id="2f8cd-102">WHERE — funkcja</span><span class="sxs-lookup"><span data-stu-id="2f8cd-102">Where function</span></span>

<span data-ttu-id="2f8cd-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2f8cd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2f8cd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2f8cd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2f8cd-105">Podano predykat i tablicę, zwraca indeksy tej tablicy, w której predykat ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="2f8cd-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="2f8cd-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2f8cd-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="2f8cd-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2f8cd-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2f8cd-108">Funkcja z `'T` do wartości logicznej, która jest używana do filtrowania elementów.</span><span class="sxs-lookup"><span data-stu-id="2f8cd-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="2f8cd-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="2f8cd-109">array : 'T[]</span></span>

<span data-ttu-id="2f8cd-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="2f8cd-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="2f8cd-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="2f8cd-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="2f8cd-112">Tablica indeksów, gdzie `predicate` ma wartość true.</span><span class="sxs-lookup"><span data-stu-id="2f8cd-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2f8cd-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2f8cd-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f8cd-114">'C</span><span class="sxs-lookup"><span data-stu-id="2f8cd-114">'T</span></span>

<span data-ttu-id="2f8cd-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="2f8cd-115">The type of `array` elements.</span></span>