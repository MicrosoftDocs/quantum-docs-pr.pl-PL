---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: b6c579df354185a2defb08cd78bce816d8cc5959
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845475"
---
# <a name="rest-function"></a><span data-ttu-id="529b2-102">Rest — funkcja</span><span class="sxs-lookup"><span data-stu-id="529b2-102">Rest function</span></span>

<span data-ttu-id="529b2-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="529b2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="529b2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="529b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="529b2-105">Tworzy tablicę, która jest równa tablicy wejściowej, z tą różnicą, że pierwszy element tablicy jest porzucany.</span><span class="sxs-lookup"><span data-stu-id="529b2-105">Creates an array that is equal to an input array except that the first array element is dropped.</span></span>

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="529b2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="529b2-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="529b2-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="529b2-107">array : 'T[]</span></span>

<span data-ttu-id="529b2-108">Tablica, której drugi do ostatniego elementu ma postać tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="529b2-108">An array whose second to last elements are to form the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="529b2-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="529b2-109">Output : 'T[]</span></span>

<span data-ttu-id="529b2-110">Tablica zawierająca elementy `array[1..Length(array) - 1]` .</span><span class="sxs-lookup"><span data-stu-id="529b2-110">An array containing the elements `array[1..Length(array) - 1]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="529b2-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="529b2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="529b2-112">'C</span><span class="sxs-lookup"><span data-stu-id="529b2-112">'T</span></span>

<span data-ttu-id="529b2-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="529b2-113">The type of the array elements.</span></span>