---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814378"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="7d9e7-102">LexographicComparison, funkcja</span><span class="sxs-lookup"><span data-stu-id="7d9e7-102">LexographicComparison function</span></span>

<span data-ttu-id="7d9e7-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7d9e7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7d9e7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d9e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d9e7-105">Dana funkcja porównywania zwraca nową funkcję, która lexographically porównuje dwie tablice.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="7d9e7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7d9e7-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="7d9e7-107">elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d9e7-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7d9e7-108">Funkcja, która porównuje dwa elementy `x` i `y` zwraca wartość, jeśli `x` jest mniejsza lub równa `y` .</span><span class="sxs-lookup"><span data-stu-id="7d9e7-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="7d9e7-109">Output: (t [], t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7d9e7-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7d9e7-110">Funkcja, która porównuje dwie tablice `xs` i `ys` zwraca, jeśli `xs` występuje przed lub `ys` w kolejności lexographical.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7d9e7-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7d9e7-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d9e7-112">'C</span><span class="sxs-lookup"><span data-stu-id="7d9e7-112">'T</span></span>

<span data-ttu-id="7d9e7-113">Typ elementów porównywanych tablic.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d9e7-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7d9e7-114">Remarks</span></span>

<span data-ttu-id="7d9e7-115">Porównanie lexographic między dwiema tablicami `xs` i `ys` jest zdefiniowane przez poniższą procedurę.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="7d9e7-116">Załóżmy, że dwa elementy `x` i `y` są równoważne, jeśli `elementComparison(x, y)` i `elementComparison(y, x)` są spełnione.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="7d9e7-117">Obie tablice są porównywane element po elemencie do momentu pierwszej pary elementów, które nie są równoważne.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="7d9e7-118">Tablica zawierająca element, który występuje po raz pierwszy zgodnie z, `elementComparison` jest określana jako pierwsza w kolejności lexographical.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="7d9e7-119">Jeśli nie zostaną znalezione żadne nierównoważne elementy, a jedna tablica jest dłuższa niż pozostałe, to krótsza tablica jest określana jako pierwsza.</span><span class="sxs-lookup"><span data-stu-id="7d9e7-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d9e7-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7d9e7-120">See Also</span></span>

- [<span data-ttu-id="7d9e7-121">Microsoft. Quantum. Arrays. posortowane</span><span class="sxs-lookup"><span data-stu-id="7d9e7-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)