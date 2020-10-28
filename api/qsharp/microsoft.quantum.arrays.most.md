---
uid: Microsoft.Quantum.Arrays.Most
title: Większość funkcji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: ca89041a4e70472e9bf7a63ffcacccb35aad527c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719001"
---
# <a name="most-function"></a><span data-ttu-id="f1a51-102">Większość funkcji</span><span class="sxs-lookup"><span data-stu-id="f1a51-102">Most function</span></span>

<span data-ttu-id="f1a51-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f1a51-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f1a51-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1a51-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1a51-105">Tworzy tablicę, która jest równa tablicy wejściowej, z tą różnicą, że ostatni element tablicy jest porzucany.</span><span class="sxs-lookup"><span data-stu-id="f1a51-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="f1a51-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f1a51-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="f1a51-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="f1a51-107">array : 'T[]</span></span>

<span data-ttu-id="f1a51-108">Tablica, której pierwszy do drugiego elementów ma postać tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="f1a51-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="f1a51-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="f1a51-109">Output : 'T[]</span></span>

<span data-ttu-id="f1a51-110">Tablica zawierająca elementy `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="f1a51-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f1a51-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f1a51-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f1a51-112">'C</span><span class="sxs-lookup"><span data-stu-id="f1a51-112">'T</span></span>

<span data-ttu-id="f1a51-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="f1a51-113">The type of the array elements.</span></span>