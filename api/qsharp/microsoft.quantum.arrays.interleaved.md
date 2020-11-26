---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funkcja z przeplotem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220964"
---
# <a name="interleaved-function"></a><span data-ttu-id="35b51-102">Funkcja z przeplotem</span><span class="sxs-lookup"><span data-stu-id="35b51-102">Interleaved function</span></span>

<span data-ttu-id="35b51-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="35b51-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="35b51-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35b51-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35b51-105">Przeplot dwóch tablic o (prawie) tym samym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="35b51-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="35b51-106">Opis</span><span class="sxs-lookup"><span data-stu-id="35b51-106">Description</span></span>

<span data-ttu-id="35b51-107">Ta funkcja zwraca przeplot dwóch tablic, rozpoczynając od pierwszego elementu z pierwszej tablicy, następnie pierwszy element z drugiej tablicy itd.</span><span class="sxs-lookup"><span data-stu-id="35b51-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="35b51-108">Pierwsza Tablica musi mieć taką samą długość jak druga, lub może mieć jeden element.</span><span class="sxs-lookup"><span data-stu-id="35b51-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="35b51-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="35b51-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="35b51-110">pierwszy: t []</span><span class="sxs-lookup"><span data-stu-id="35b51-110">first : 'T[]</span></span>

<span data-ttu-id="35b51-111">Pierwsza tablica, która ma zostać przeplatana.</span><span class="sxs-lookup"><span data-stu-id="35b51-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="35b51-112">Second: t []</span><span class="sxs-lookup"><span data-stu-id="35b51-112">second : 'T[]</span></span>

<span data-ttu-id="35b51-113">Druga tablica, która ma zostać przeplatana.</span><span class="sxs-lookup"><span data-stu-id="35b51-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="35b51-114">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="35b51-114">Output : 'T[]</span></span>

<span data-ttu-id="35b51-115">Tablica z przeplotem</span><span class="sxs-lookup"><span data-stu-id="35b51-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="35b51-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="35b51-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="35b51-117">'C</span><span class="sxs-lookup"><span data-stu-id="35b51-117">'T</span></span>

<span data-ttu-id="35b51-118">Typ każdego elementu elementów `first` i `second` .</span><span class="sxs-lookup"><span data-stu-id="35b51-118">The type of each element of `first` and `second`.</span></span>