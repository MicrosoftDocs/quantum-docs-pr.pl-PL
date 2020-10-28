---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkcja systemu Windows
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718749"
---
# <a name="windows-function"></a><span data-ttu-id="8a694-102">Funkcja systemu Windows</span><span class="sxs-lookup"><span data-stu-id="8a694-102">Windows function</span></span>

<span data-ttu-id="8a694-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8a694-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8a694-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8a694-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8a694-105">Zwraca wszystkie kolejne podtablice długości `size` .</span><span class="sxs-lookup"><span data-stu-id="8a694-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="8a694-106">Opis</span><span class="sxs-lookup"><span data-stu-id="8a694-106">Description</span></span>

<span data-ttu-id="8a694-107">Ta funkcja zwraca wszystkie `n - size + 1` podtablice długości `size` w kolejności, gdzie `n` jest długością `arr` .</span><span class="sxs-lookup"><span data-stu-id="8a694-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="8a694-108">Pierwsze podtablice są `arr[0..size - 1], arr[1..size], arr[2..size + 1]` do momentu ostatniej podtablicy `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="8a694-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="8a694-109">Jeśli `size <= 0` lub `size > n` , zwracana jest pusta tablica.</span><span class="sxs-lookup"><span data-stu-id="8a694-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="8a694-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8a694-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="8a694-111">rozmiar: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8a694-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8a694-112">Długość podtablic.</span><span class="sxs-lookup"><span data-stu-id="8a694-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="8a694-113">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="8a694-113">array : 'T[]</span></span>

<span data-ttu-id="8a694-114">Tablica elementów.</span><span class="sxs-lookup"><span data-stu-id="8a694-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="8a694-115">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="8a694-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8a694-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8a694-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8a694-117">'C</span><span class="sxs-lookup"><span data-stu-id="8a694-117">'T</span></span>

<span data-ttu-id="8a694-118">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="8a694-118">The type of `array` elements.</span></span>