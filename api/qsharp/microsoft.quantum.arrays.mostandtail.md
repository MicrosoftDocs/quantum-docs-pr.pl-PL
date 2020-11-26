---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220573"
---
# <a name="mostandtail-function"></a><span data-ttu-id="d67eb-102">MostAndTail, funkcja</span><span class="sxs-lookup"><span data-stu-id="d67eb-102">MostAndTail function</span></span>

<span data-ttu-id="d67eb-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d67eb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d67eb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d67eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d67eb-105">Zwraca krotkę wszystkich elementów oprócz jednego i ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="d67eb-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="d67eb-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d67eb-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="d67eb-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="d67eb-107">array : 'A[]</span></span>

<span data-ttu-id="d67eb-108">Tablica z co najmniej jednym elementem.</span><span class="sxs-lookup"><span data-stu-id="d67eb-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="d67eb-109">Wynik: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="d67eb-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="d67eb-110">Krotka wszystkich elementów oprócz jednego i ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="d67eb-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d67eb-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d67eb-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="d67eb-112">"A</span><span class="sxs-lookup"><span data-stu-id="d67eb-112">'A</span></span>

<span data-ttu-id="d67eb-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="d67eb-113">The type of the array elements.</span></span>