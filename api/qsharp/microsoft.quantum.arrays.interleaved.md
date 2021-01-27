---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Funkcja z przeplotem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848112"
---
# <a name="interleaved-function"></a><span data-ttu-id="fe954-102">Funkcja z przeplotem</span><span class="sxs-lookup"><span data-stu-id="fe954-102">Interleaved function</span></span>

<span data-ttu-id="fe954-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fe954-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fe954-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fe954-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fe954-105">Przeplot dwóch tablic o (prawie) tym samym rozmiarze.</span><span class="sxs-lookup"><span data-stu-id="fe954-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="fe954-106">Opis</span><span class="sxs-lookup"><span data-stu-id="fe954-106">Description</span></span>

<span data-ttu-id="fe954-107">Ta funkcja zwraca przeplot dwóch tablic, rozpoczynając od pierwszego elementu z pierwszej tablicy, następnie pierwszy element z drugiej tablicy itd.</span><span class="sxs-lookup"><span data-stu-id="fe954-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="fe954-108">Pierwsza Tablica musi mieć taką samą długość jak druga, lub może mieć jeden element.</span><span class="sxs-lookup"><span data-stu-id="fe954-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="fe954-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fe954-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="fe954-110">pierwszy: t []</span><span class="sxs-lookup"><span data-stu-id="fe954-110">first : 'T[]</span></span>

<span data-ttu-id="fe954-111">Pierwsza tablica, która ma zostać przeplatana.</span><span class="sxs-lookup"><span data-stu-id="fe954-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="fe954-112">Second: t []</span><span class="sxs-lookup"><span data-stu-id="fe954-112">second : 'T[]</span></span>

<span data-ttu-id="fe954-113">Druga tablica, która ma zostać przeplatana.</span><span class="sxs-lookup"><span data-stu-id="fe954-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="fe954-114">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="fe954-114">Output : 'T[]</span></span>

<span data-ttu-id="fe954-115">Tablica z przeplotem</span><span class="sxs-lookup"><span data-stu-id="fe954-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fe954-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fe954-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe954-117">'C</span><span class="sxs-lookup"><span data-stu-id="fe954-117">'T</span></span>

<span data-ttu-id="fe954-118">Typ każdego elementu elementów `first` i `second` .</span><span class="sxs-lookup"><span data-stu-id="fe954-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="fe954-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="fe954-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```