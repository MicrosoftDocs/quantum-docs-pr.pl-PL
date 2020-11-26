---
uid: Microsoft.Quantum.Arrays.Most
title: Większość funkcji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Most
qsharp.summary: Creates an array that is equal to an input array except that the last array element is dropped.
ms.openlocfilehash: 81e66e0b64ae8dfc44d163b68370ccadd191c729
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220607"
---
# <a name="most-function"></a><span data-ttu-id="45c88-102">Większość funkcji</span><span class="sxs-lookup"><span data-stu-id="45c88-102">Most function</span></span>

<span data-ttu-id="45c88-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="45c88-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="45c88-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45c88-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45c88-105">Tworzy tablicę, która jest równa tablicy wejściowej, z tą różnicą, że ostatni element tablicy jest porzucany.</span><span class="sxs-lookup"><span data-stu-id="45c88-105">Creates an array that is equal to an input array except that the last array element is dropped.</span></span>

```qsharp
function Most<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="45c88-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="45c88-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="45c88-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="45c88-107">array : 'T[]</span></span>

<span data-ttu-id="45c88-108">Tablica, której pierwszy do drugiego elementów ma postać tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="45c88-108">An array whose first to second-to-last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="45c88-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="45c88-109">Output : 'T[]</span></span>

<span data-ttu-id="45c88-110">Tablica zawierająca elementy `array[0..Length(array) - 2]` .</span><span class="sxs-lookup"><span data-stu-id="45c88-110">An array containing the elements `array[0..Length(array) - 2]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45c88-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="45c88-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45c88-112">'C</span><span class="sxs-lookup"><span data-stu-id="45c88-112">'T</span></span>

<span data-ttu-id="45c88-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="45c88-113">The type of the array elements.</span></span>