---
uid: Microsoft.Quantum.Arrays.Windows
title: Funkcja systemu Windows
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219893"
---
# <a name="windows-function"></a><span data-ttu-id="03a9d-102">Funkcja systemu Windows</span><span class="sxs-lookup"><span data-stu-id="03a9d-102">Windows function</span></span>

<span data-ttu-id="03a9d-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="03a9d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="03a9d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03a9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03a9d-105">Zwraca wszystkie kolejne podtablice długości `size` .</span><span class="sxs-lookup"><span data-stu-id="03a9d-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="03a9d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="03a9d-106">Description</span></span>

<span data-ttu-id="03a9d-107">Ta funkcja zwraca wszystkie `n - size + 1` podtablice długości `size` w kolejności, gdzie `n` jest długością `arr` .</span><span class="sxs-lookup"><span data-stu-id="03a9d-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="03a9d-108">Pierwsze podtablice są `arr[0..size - 1], arr[1..size], arr[2..size + 1]` do momentu ostatniej podtablicy `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="03a9d-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="03a9d-109">Jeśli `size <= 0` lub `size > n` , zwracana jest pusta tablica.</span><span class="sxs-lookup"><span data-stu-id="03a9d-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="03a9d-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="03a9d-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="03a9d-111">rozmiar: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03a9d-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03a9d-112">Długość podtablic.</span><span class="sxs-lookup"><span data-stu-id="03a9d-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="03a9d-113">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="03a9d-113">array : 'T[]</span></span>

<span data-ttu-id="03a9d-114">Tablica elementów.</span><span class="sxs-lookup"><span data-stu-id="03a9d-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="03a9d-115">Wynik: t [] []</span><span class="sxs-lookup"><span data-stu-id="03a9d-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="03a9d-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="03a9d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03a9d-117">'C</span><span class="sxs-lookup"><span data-stu-id="03a9d-117">'T</span></span>

<span data-ttu-id="03a9d-118">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="03a9d-118">The type of `array` elements.</span></span>