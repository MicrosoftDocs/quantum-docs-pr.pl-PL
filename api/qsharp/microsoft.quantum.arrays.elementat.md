---
uid: Microsoft.Quantum.Arrays.ElementAt
title: ElementAt, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842817"
---
# <a name="elementat-function"></a><span data-ttu-id="57a9b-102">ElementAt, funkcja</span><span class="sxs-lookup"><span data-stu-id="57a9b-102">ElementAt function</span></span>

<span data-ttu-id="57a9b-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="57a9b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="57a9b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="57a9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="57a9b-105">Zwraca wartość przy podanym indeksie tablicy.</span><span class="sxs-lookup"><span data-stu-id="57a9b-105">Returns the at the given index of an array.</span></span>

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a><span data-ttu-id="57a9b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="57a9b-106">Input</span></span>

### <a name="index--int"></a><span data-ttu-id="57a9b-107">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="57a9b-107">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="57a9b-108">Indeks elementu</span><span class="sxs-lookup"><span data-stu-id="57a9b-108">Index of element</span></span>


### <a name="array--t"></a><span data-ttu-id="57a9b-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="57a9b-109">array : 'T[]</span></span>

<span data-ttu-id="57a9b-110">Tablica jest indeksowana.</span><span class="sxs-lookup"><span data-stu-id="57a9b-110">The array being indexed.</span></span>



## <a name="output--t"></a><span data-ttu-id="57a9b-111">Dane wyjściowe: 'T</span><span class="sxs-lookup"><span data-stu-id="57a9b-111">Output : 'T</span></span>



## <a name="type-parameters"></a><span data-ttu-id="57a9b-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="57a9b-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="57a9b-113">'C</span><span class="sxs-lookup"><span data-stu-id="57a9b-113">'T</span></span>

<span data-ttu-id="57a9b-114">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="57a9b-114">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="57a9b-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="57a9b-115">Example</span></span>

<span data-ttu-id="57a9b-116">Uzyskaj trzecią liczbę w czterech sławę liczbach całkowitych.</span><span class="sxs-lookup"><span data-stu-id="57a9b-116">Get the third number in four famous integer sequences.</span></span> <span data-ttu-id="57a9b-117">(należy zauważyć, że indeks 0 odpowiada _pierwszej_ wartości sekwencji).</span><span class="sxs-lookup"><span data-stu-id="57a9b-117">(note that the 0 index corresponds to the _first_ value of the sequence.)</span></span>

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a><span data-ttu-id="57a9b-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="57a9b-118">See Also</span></span>

- [<span data-ttu-id="57a9b-119">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="57a9b-119">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [<span data-ttu-id="57a9b-120">Microsoft. Quantum. Arrays. ElementsAt</span><span class="sxs-lookup"><span data-stu-id="57a9b-120">Microsoft.Quantum.Arrays.ElementsAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementsAt)