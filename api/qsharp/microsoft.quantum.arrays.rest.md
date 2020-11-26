---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: 4dd10b6e8839fd906ca9c2e36c89c626d5772149
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220399"
---
# <a name="rest-function"></a><span data-ttu-id="5b12c-102">Rest — funkcja</span><span class="sxs-lookup"><span data-stu-id="5b12c-102">Rest function</span></span>

<span data-ttu-id="5b12c-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5b12c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5b12c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5b12c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5b12c-105">Tworzy tablicę, która jest równa tablicy wejściowej, z tą różnicą, że pierwszy element tablicy jest porzucany.</span><span class="sxs-lookup"><span data-stu-id="5b12c-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5b12c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5b12c-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="5b12c-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="5b12c-107">array : 'T[]</span></span>

<span data-ttu-id="5b12c-108">Tablica, której drugi do ostatniego elementu ma postać tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="5b12c-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="5b12c-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="5b12c-109">Output : 'T[]</span></span>

<span data-ttu-id="5b12c-110">Tablica zawierająca elementy `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="5b12c-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5b12c-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5b12c-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5b12c-112">'C</span><span class="sxs-lookup"><span data-stu-id="5b12c-112">'T</span></span>

<span data-ttu-id="5b12c-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="5b12c-113">The type of the array elements.</span></span>