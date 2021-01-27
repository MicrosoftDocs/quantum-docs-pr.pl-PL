---
uid: Microsoft.Quantum.Arrays.Most
title: Większość funkcji
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 2b212b38ec55f3798eb9397f03b842573173eb88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845579"
---
# <a name="most-function"></a><span data-ttu-id="a983f-102">Większość funkcji</span><span class="sxs-lookup"><span data-stu-id="a983f-102">Most function</span></span>

<span data-ttu-id="a983f-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a983f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a983f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a983f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a983f-105">Tworzy tablicę, która jest równa tablicy wejściowej, z tą różnicą, że ostatni element tablicy jest porzucany.</span><span class="sxs-lookup"><span data-stu-id="a983f-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a983f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a983f-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="a983f-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="a983f-107">array : 'T[]</span></span>

<span data-ttu-id="a983f-108">Tablica, której pierwszy do drugiego elementów ma postać tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="a983f-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="a983f-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="a983f-109">Output : 'T[]</span></span>

<span data-ttu-id="a983f-110">Tablica zawierająca elementy `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="a983f-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a983f-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a983f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a983f-112">'C</span><span class="sxs-lookup"><span data-stu-id="a983f-112">'T</span></span>

<span data-ttu-id="a983f-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="a983f-113">The type of the array elements.</span></span>