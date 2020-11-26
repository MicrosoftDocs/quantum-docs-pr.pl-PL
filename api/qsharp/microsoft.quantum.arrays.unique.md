---
uid: Microsoft.Quantum.Arrays.Unique
title: Funkcja unikatowa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220012"
---
# <a name="unique-function"></a><span data-ttu-id="26532-102">Funkcja unikatowa</span><span class="sxs-lookup"><span data-stu-id="26532-102">Unique function</span></span>

<span data-ttu-id="26532-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="26532-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="26532-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26532-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26532-105">Zwraca nową tablicę, która nie ma równych elementów sąsiadujących.</span><span class="sxs-lookup"><span data-stu-id="26532-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="26532-106">Opis</span><span class="sxs-lookup"><span data-stu-id="26532-106">Description</span></span>

<span data-ttu-id="26532-107">Dana Tablica elementów i funkcja do testowania równości, ta funkcja zwraca nową tablicę, w której jest przechowywana względna kolejność elementów, ale wszystkie sąsiadujące elementy, które są równe są filtrowane do pojedynczego elementu.</span><span class="sxs-lookup"><span data-stu-id="26532-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="26532-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="26532-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="26532-109">równe: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="26532-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="26532-110">Funkcja, która porównuje dwa elementy, które `a` są uważane za równe `b` , `equal(a, b)` Jeśli jest `true` .</span><span class="sxs-lookup"><span data-stu-id="26532-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="26532-111">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="26532-111">array : 'T[]</span></span>

<span data-ttu-id="26532-112">Tablica, która ma zostać przefiltrowana pod kątem unikatowych elementów.</span><span class="sxs-lookup"><span data-stu-id="26532-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="26532-113">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="26532-113">Output : 'T[]</span></span>

<span data-ttu-id="26532-114">Tablica bez równych elementów sąsiadujących.</span><span class="sxs-lookup"><span data-stu-id="26532-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="26532-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="26532-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="26532-116">'C</span><span class="sxs-lookup"><span data-stu-id="26532-116">'T</span></span>

<span data-ttu-id="26532-117">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="26532-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="26532-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="26532-118">Remarks</span></span>

<span data-ttu-id="26532-119">Jeśli istnieje wiele elementów, które są równe, ale nie obok siebie, w tablicy wyjściowej będzie wiele wystąpień.</span><span class="sxs-lookup"><span data-stu-id="26532-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="26532-120">Użyj tej funkcji razem z `Sorted` , aby uzyskać tablicę z ogólnymi unikatowymi elementami.</span><span class="sxs-lookup"><span data-stu-id="26532-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>