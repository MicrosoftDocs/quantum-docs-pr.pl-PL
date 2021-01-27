---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845603"
---
# <a name="mostandtail-function"></a><span data-ttu-id="f0098-102">MostAndTail, funkcja</span><span class="sxs-lookup"><span data-stu-id="f0098-102">MostAndTail function</span></span>

<span data-ttu-id="f0098-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f0098-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f0098-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0098-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0098-105">Zwraca krotkę wszystkich elementów oprócz jednego i ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="f0098-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="f0098-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f0098-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="f0098-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="f0098-107">array : 'A[]</span></span>

<span data-ttu-id="f0098-108">Tablica z co najmniej jednym elementem.</span><span class="sxs-lookup"><span data-stu-id="f0098-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="f0098-109">Wynik: (' A [], ' A)</span><span class="sxs-lookup"><span data-stu-id="f0098-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="f0098-110">Krotka wszystkich elementów oprócz jednego i ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="f0098-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0098-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f0098-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="f0098-112">"A</span><span class="sxs-lookup"><span data-stu-id="f0098-112">'A</span></span>

<span data-ttu-id="f0098-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="f0098-113">The type of the array elements.</span></span>