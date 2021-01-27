---
uid: Microsoft.Quantum.Arrays.Chunks
title: Funkcja fragmentów
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842876"
---
# <a name="chunks-function"></a><span data-ttu-id="ce3ce-102">Funkcja fragmentów</span><span class="sxs-lookup"><span data-stu-id="ce3ce-102">Chunks function</span></span>

<span data-ttu-id="ce3ce-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ce3ce-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ce3ce-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ce3ce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ce3ce-105">Dzieli tablicę na wiele części równej długości.</span><span class="sxs-lookup"><span data-stu-id="ce3ce-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="ce3ce-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ce3ce-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="ce3ce-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ce3ce-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ce3ce-108">Długość każdego fragmentu.</span><span class="sxs-lookup"><span data-stu-id="ce3ce-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="ce3ce-109">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="ce3ce-109">arr : 'T[]</span></span>

<span data-ttu-id="ce3ce-110">Tablica, która ma zostać podzielona.</span><span class="sxs-lookup"><span data-stu-id="ce3ce-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="ce3ce-111">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="ce3ce-111">Output : 'T[][]</span></span>

<span data-ttu-id="ce3ce-112">Tablica zawierająca każdy fragment oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="ce3ce-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ce3ce-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ce3ce-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ce3ce-114">'C</span><span class="sxs-lookup"><span data-stu-id="ce3ce-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="ce3ce-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ce3ce-115">Remarks</span></span>

<span data-ttu-id="ce3ce-116">Należy zauważyć, że ostatni element danych wyjściowych może być krótszy niż `nElements` Jeśli `Length(arr)` nie jest podzielny przez `nElements` .</span><span class="sxs-lookup"><span data-stu-id="ce3ce-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>