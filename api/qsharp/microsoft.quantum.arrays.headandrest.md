---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719181"
---
# <a name="headandrest-function"></a><span data-ttu-id="de41a-102">HeadAndRest, funkcja</span><span class="sxs-lookup"><span data-stu-id="de41a-102">HeadAndRest function</span></span>

<span data-ttu-id="de41a-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="de41a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="de41a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de41a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de41a-105">Zwraca krotkę pierwszych i pozostałych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="de41a-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="de41a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="de41a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="de41a-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="de41a-107">array : 'A[]</span></span>

<span data-ttu-id="de41a-108">Tablica z co najmniej jednym elementem.</span><span class="sxs-lookup"><span data-stu-id="de41a-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="de41a-109">Wynik: ("A," A [])</span><span class="sxs-lookup"><span data-stu-id="de41a-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="de41a-110">Spójna kolekcja pierwszych i pozostałych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="de41a-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="de41a-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="de41a-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="de41a-112">"A</span><span class="sxs-lookup"><span data-stu-id="de41a-112">'A</span></span>

<span data-ttu-id="de41a-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="de41a-113">The type of the array elements.</span></span>