---
uid: Microsoft.Quantum.Arrays.TupleArrayAsNestedArray
title: TupleArrayAsNestedArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: TupleArrayAsNestedArray
qsharp.summary: Turns a list of 2-tuples into a nested array.
ms.openlocfilehash: 51a35555080d1d2475fc1aa9e48e84c7c6f92c51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845390"
---
# <a name="tuplearrayasnestedarray-function"></a><span data-ttu-id="ec147-102">TupleArrayAsNestedArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="ec147-102">TupleArrayAsNestedArray function</span></span>

<span data-ttu-id="ec147-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ec147-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ec147-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec147-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec147-105">Zamienia listę 2-kroteks na tablicę zagnieżdżoną.</span><span class="sxs-lookup"><span data-stu-id="ec147-105">Turns a list of 2-tuples into a nested array.</span></span>

```qsharp
function TupleArrayAsNestedArray<'T> (tupleList : ('T, 'T)[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="ec147-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ec147-106">Input</span></span>

### <a name="tuplelist--tt"></a><span data-ttu-id="ec147-107">tupleList: (t, t) []</span><span class="sxs-lookup"><span data-stu-id="ec147-107">tupleList : ('T,'T)[]</span></span>

<span data-ttu-id="ec147-108">Lista 2-krotek, która ma zostać przekształcona w tablicę zagnieżdżoną.</span><span class="sxs-lookup"><span data-stu-id="ec147-108">List of 2-tuples to be turned into a nested array.</span></span>



## <a name="output--t"></a><span data-ttu-id="ec147-109">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="ec147-109">Output : 'T[][]</span></span>

<span data-ttu-id="ec147-110">Zagnieżdżona tablica o długości zgodnej z tupleList.</span><span class="sxs-lookup"><span data-stu-id="ec147-110">A nested array with length matching the tupleList.</span></span>

## <a name="example"></a><span data-ttu-id="ec147-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="ec147-111">Example</span></span>

```qsharp
// The following returns [[2, 3], [4, 5]]
TupleArrayAsNestedArray([(2, 3), (4, 5)]);
```

## <a name="type-parameters"></a><span data-ttu-id="ec147-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ec147-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ec147-113">'C</span><span class="sxs-lookup"><span data-stu-id="ec147-113">'T</span></span>

