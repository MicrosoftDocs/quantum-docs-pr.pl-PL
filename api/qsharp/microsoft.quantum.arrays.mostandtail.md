---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718992"
---
# <a name="mostandtail-function"></a><span data-ttu-id="07b7f-102">MostAndTail, funkcja</span><span class="sxs-lookup"><span data-stu-id="07b7f-102">MostAndTail function</span></span>

<span data-ttu-id="07b7f-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="07b7f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="07b7f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07b7f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07b7f-105">Zwraca krotkę wszystkich elementów oprócz jednego i ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="07b7f-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="07b7f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="07b7f-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="07b7f-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="07b7f-107">array : 'A[]</span></span>

<span data-ttu-id="07b7f-108">Tablica z co najmniej jednym elementem.</span><span class="sxs-lookup"><span data-stu-id="07b7f-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="07b7f-109">Wynik: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="07b7f-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="07b7f-110">Krotka wszystkich elementów oprócz jednego i ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="07b7f-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07b7f-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="07b7f-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="07b7f-112">"A</span><span class="sxs-lookup"><span data-stu-id="07b7f-112">'A</span></span>

<span data-ttu-id="07b7f-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="07b7f-113">The type of the array elements.</span></span>