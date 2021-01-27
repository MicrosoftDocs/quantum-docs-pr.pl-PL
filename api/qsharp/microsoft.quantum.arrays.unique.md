---
uid: Microsoft.Quantum.Arrays.Unique
title: Funkcja unikatowa
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850923"
---
# <a name="unique-function"></a><span data-ttu-id="43da2-102">Funkcja unikatowa</span><span class="sxs-lookup"><span data-stu-id="43da2-102">Unique function</span></span>

<span data-ttu-id="43da2-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="43da2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="43da2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="43da2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="43da2-105">Zwraca nową tablicę, która nie ma równych elementów sąsiadujących.</span><span class="sxs-lookup"><span data-stu-id="43da2-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="43da2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="43da2-106">Description</span></span>

<span data-ttu-id="43da2-107">Dana Tablica elementów i funkcja do testowania równości, ta funkcja zwraca nową tablicę, w której jest przechowywana względna kolejność elementów, ale wszystkie sąsiadujące elementy, które są równe są filtrowane do pojedynczego elementu.</span><span class="sxs-lookup"><span data-stu-id="43da2-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="43da2-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="43da2-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="43da2-109">równe: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="43da2-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="43da2-110">Funkcja, która porównuje dwa elementy, które `a` są uważane za równe `b` , `equal(a, b)` Jeśli jest `true` .</span><span class="sxs-lookup"><span data-stu-id="43da2-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="43da2-111">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="43da2-111">array : 'T[]</span></span>

<span data-ttu-id="43da2-112">Tablica, która ma zostać przefiltrowana pod kątem unikatowych elementów.</span><span class="sxs-lookup"><span data-stu-id="43da2-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="43da2-113">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="43da2-113">Output : 'T[]</span></span>

<span data-ttu-id="43da2-114">Tablica bez równych elementów sąsiadujących.</span><span class="sxs-lookup"><span data-stu-id="43da2-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="43da2-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="43da2-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="43da2-116">'C</span><span class="sxs-lookup"><span data-stu-id="43da2-116">'T</span></span>

<span data-ttu-id="43da2-117">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="43da2-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="43da2-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="43da2-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="43da2-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="43da2-119">Remarks</span></span>

<span data-ttu-id="43da2-120">Jeśli istnieje wiele elementów, które są równe, ale nie obok siebie, w tablicy wyjściowej będzie wiele wystąpień.</span><span class="sxs-lookup"><span data-stu-id="43da2-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="43da2-121">Użyj tej funkcji razem z `Sorted` , aby uzyskać tablicę z ogólnymi unikatowymi elementami.</span><span class="sxs-lookup"><span data-stu-id="43da2-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>