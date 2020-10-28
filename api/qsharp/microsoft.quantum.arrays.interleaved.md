---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funkcja z przeplotem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719145"
---
# <a name="interleaved-function"></a><span data-ttu-id="713da-102">Funkcja z przeplotem</span><span class="sxs-lookup"><span data-stu-id="713da-102">Interleaved function</span></span>

<span data-ttu-id="713da-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="713da-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="713da-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="713da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="713da-105">Przeplot dwóch tablic o (prawie) tym samym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="713da-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="713da-106">Opis</span><span class="sxs-lookup"><span data-stu-id="713da-106">Description</span></span>

<span data-ttu-id="713da-107">Ta funkcja zwraca przeplot dwóch tablic, rozpoczynając od pierwszego elementu z pierwszej tablicy, następnie pierwszy element z drugiej tablicy itd.</span><span class="sxs-lookup"><span data-stu-id="713da-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="713da-108">Pierwsza Tablica musi mieć taką samą długość jak druga, lub może mieć jeden element.</span><span class="sxs-lookup"><span data-stu-id="713da-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="713da-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="713da-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="713da-110">pierwszy: t []</span><span class="sxs-lookup"><span data-stu-id="713da-110">first : 'T[]</span></span>

<span data-ttu-id="713da-111">Pierwsza tablica, która ma zostać przeplatana.</span><span class="sxs-lookup"><span data-stu-id="713da-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="713da-112">Second: t []</span><span class="sxs-lookup"><span data-stu-id="713da-112">second : 'T[]</span></span>

<span data-ttu-id="713da-113">Druga tablica, która ma zostać przeplatana.</span><span class="sxs-lookup"><span data-stu-id="713da-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="713da-114">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="713da-114">Output : 'T[]</span></span>

<span data-ttu-id="713da-115">Tablica z przeplotem</span><span class="sxs-lookup"><span data-stu-id="713da-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="713da-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="713da-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="713da-117">'C</span><span class="sxs-lookup"><span data-stu-id="713da-117">'T</span></span>

<span data-ttu-id="713da-118">Typ każdego elementu elementów `first` i `second` .</span><span class="sxs-lookup"><span data-stu-id="713da-118">The type of each element of `first` and `second`.</span></span>