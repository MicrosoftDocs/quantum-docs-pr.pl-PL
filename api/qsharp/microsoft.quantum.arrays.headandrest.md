---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848559"
---
# <a name="headandrest-function"></a><span data-ttu-id="a49d5-102">HeadAndRest, funkcja</span><span class="sxs-lookup"><span data-stu-id="a49d5-102">HeadAndRest function</span></span>

<span data-ttu-id="a49d5-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a49d5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a49d5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a49d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a49d5-105">Zwraca krotkę pierwszych i pozostałych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="a49d5-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="a49d5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a49d5-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="a49d5-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="a49d5-107">array : 'A[]</span></span>

<span data-ttu-id="a49d5-108">Tablica z co najmniej jednym elementem.</span><span class="sxs-lookup"><span data-stu-id="a49d5-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="a49d5-109">Wynik: ("A," A [])</span><span class="sxs-lookup"><span data-stu-id="a49d5-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="a49d5-110">Spójna kolekcja pierwszych i pozostałych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="a49d5-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a49d5-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a49d5-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="a49d5-112">"A</span><span class="sxs-lookup"><span data-stu-id="a49d5-112">'A</span></span>

<span data-ttu-id="a49d5-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="a49d5-113">The type of the array elements.</span></span>