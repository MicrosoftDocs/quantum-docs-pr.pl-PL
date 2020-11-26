---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkcja fragmentów
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221610"
---
# <a name="chunks-function"></a><span data-ttu-id="3f56f-102">Funkcja fragmentów</span><span class="sxs-lookup"><span data-stu-id="3f56f-102">Chunks function</span></span>

<span data-ttu-id="3f56f-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3f56f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3f56f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3f56f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3f56f-105">Dzieli tablicę na wiele części równej długości.</span><span class="sxs-lookup"><span data-stu-id="3f56f-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="3f56f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3f56f-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="3f56f-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3f56f-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3f56f-108">Długość każdego fragmentu.</span><span class="sxs-lookup"><span data-stu-id="3f56f-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="3f56f-109">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="3f56f-109">arr : 'T[]</span></span>

<span data-ttu-id="3f56f-110">Tablica, która ma zostać podzielona.</span><span class="sxs-lookup"><span data-stu-id="3f56f-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="3f56f-111">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="3f56f-111">Output : 'T[][]</span></span>

<span data-ttu-id="3f56f-112">Tablica zawierająca każdy fragment oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="3f56f-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3f56f-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3f56f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3f56f-114">'C</span><span class="sxs-lookup"><span data-stu-id="3f56f-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="3f56f-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3f56f-115">Remarks</span></span>

<span data-ttu-id="3f56f-116">Należy zauważyć, że ostatni element danych wyjściowych może być krótszy niż `nElements` Jeśli `Length(arr)` nie jest podzielny przez `nElements` .</span><span class="sxs-lookup"><span data-stu-id="3f56f-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>