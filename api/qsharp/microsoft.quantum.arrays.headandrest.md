---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221083"
---
# <a name="headandrest-function"></a><span data-ttu-id="fcbec-102">HeadAndRest, funkcja</span><span class="sxs-lookup"><span data-stu-id="fcbec-102">HeadAndRest function</span></span>

<span data-ttu-id="fcbec-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fcbec-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fcbec-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fcbec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fcbec-105">Zwraca krotkę pierwszych i pozostałych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="fcbec-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="fcbec-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fcbec-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="fcbec-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="fcbec-107">array : 'A[]</span></span>

<span data-ttu-id="fcbec-108">Tablica z co najmniej jednym elementem.</span><span class="sxs-lookup"><span data-stu-id="fcbec-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="fcbec-109">Wynik: ("A," A [])</span><span class="sxs-lookup"><span data-stu-id="fcbec-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="fcbec-110">Spójna kolekcja pierwszych i pozostałych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="fcbec-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fcbec-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fcbec-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="fcbec-112">"A</span><span class="sxs-lookup"><span data-stu-id="fcbec-112">'A</span></span>

<span data-ttu-id="fcbec-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="fcbec-113">The type of the array elements.</span></span>