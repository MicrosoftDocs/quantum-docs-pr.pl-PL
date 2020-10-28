---
uid: Microsoft.Quantum.Arrays.Sorted
title: Funkcja posortowana
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718884"
---
# <a name="sorted-function"></a><span data-ttu-id="9c44d-102">Funkcja posortowana</span><span class="sxs-lookup"><span data-stu-id="9c44d-102">Sorted function</span></span>

<span data-ttu-id="9c44d-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9c44d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9c44d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c44d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c44d-105">Dana tablica zwraca elementy tej tablicy posortowane według danej funkcji porównywania.</span><span class="sxs-lookup"><span data-stu-id="9c44d-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9c44d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9c44d-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="9c44d-107">Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9c44d-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9c44d-108">Funkcja, która porównuje dwa elementy, które `a` są uważane za mniej niż lub równą `b` if `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="9c44d-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="9c44d-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="9c44d-109">array : 'T[]</span></span>

<span data-ttu-id="9c44d-110">Tablica, która ma zostać posortowana.</span><span class="sxs-lookup"><span data-stu-id="9c44d-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="9c44d-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="9c44d-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9c44d-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9c44d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9c44d-113">'C</span><span class="sxs-lookup"><span data-stu-id="9c44d-113">'T</span></span>

<span data-ttu-id="9c44d-114">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="9c44d-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="9c44d-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9c44d-115">Remarks</span></span>

<span data-ttu-id="9c44d-116">Przyjmuje się `comparison` , że funkcja jest przechodnia, na przykład jeśli `comparison(a, b)` i `comparison(b, c)` , `comparison(a, c)` jest przyjmowana.</span><span class="sxs-lookup"><span data-stu-id="9c44d-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="9c44d-117">Jeśli ta właściwość nie jest wstrzymana, dane wyjściowe tej funkcji mogą być nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="9c44d-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="9c44d-118">Ponieważ jest to funkcja, wyniki są całkowicie determinstic, nawet jeśli dwa elementy są uważane za równe `comparison` . to jest, kiedy `comparison(a, b)` i `comparison(b, a)` są oba `true` .</span><span class="sxs-lookup"><span data-stu-id="9c44d-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="9c44d-119">W szczególności sortowanie wykonywane przez tę funkcję jest gwarantowane jako stabilne, więc jeśli dwa elementy `a` i `b` występują w tej kolejności w `array` i są uznawane za równe w `comparison` , a następnie `a` pojawią się przed `b` w danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="9c44d-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="9c44d-120">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="9c44d-120">For example:</span></span>

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```