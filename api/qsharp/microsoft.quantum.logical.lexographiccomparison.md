---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709907"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="94a06-102">LexographicComparison, funkcja</span><span class="sxs-lookup"><span data-stu-id="94a06-102">LexographicComparison function</span></span>

<span data-ttu-id="94a06-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="94a06-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="94a06-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="94a06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="94a06-105">Dana funkcja porównywania zwraca nową funkcję, która lexographically porównuje dwie tablice.</span><span class="sxs-lookup"><span data-stu-id="94a06-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="94a06-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="94a06-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="94a06-107">elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="94a06-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="94a06-108">Funkcja, która porównuje dwa elementy `x` i `y` zwraca wartość, jeśli `x` jest mniejsza lub równa `y` .</span><span class="sxs-lookup"><span data-stu-id="94a06-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="94a06-109">Output: (t [], t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="94a06-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="94a06-110">Funkcja, która porównuje dwie tablice `xs` i `ys` zwraca, jeśli `xs` występuje przed lub `ys` w kolejności lexographical.</span><span class="sxs-lookup"><span data-stu-id="94a06-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="94a06-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="94a06-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94a06-112">'C</span><span class="sxs-lookup"><span data-stu-id="94a06-112">'T</span></span>

<span data-ttu-id="94a06-113">Typ elementów porównywanych tablic.</span><span class="sxs-lookup"><span data-stu-id="94a06-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="94a06-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="94a06-114">Remarks</span></span>

<span data-ttu-id="94a06-115">Porównanie lexographic między dwiema tablicami `xs` i `ys` jest zdefiniowane przez poniższą procedurę.</span><span class="sxs-lookup"><span data-stu-id="94a06-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="94a06-116">Załóżmy, że dwa elementy `x` i `y` są równoważne, jeśli `elementComparison(x, y)` i `elementComparison(y, x)` są spełnione.</span><span class="sxs-lookup"><span data-stu-id="94a06-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="94a06-117">Obie tablice są porównywane element po elemencie do momentu pierwszej pary elementów, które nie są równoważne.</span><span class="sxs-lookup"><span data-stu-id="94a06-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="94a06-118">Tablica zawierająca element, który występuje po raz pierwszy zgodnie z, `elementComparison` jest określana jako pierwsza w kolejności lexographical.</span><span class="sxs-lookup"><span data-stu-id="94a06-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="94a06-119">Jeśli nie zostaną znalezione żadne nierównoważne elementy, a jedna tablica jest dłuższa niż pozostałe, to krótsza tablica jest określana jako pierwsza.</span><span class="sxs-lookup"><span data-stu-id="94a06-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="94a06-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="94a06-120">See Also</span></span>

- [<span data-ttu-id="94a06-121">Microsoft. Quantum. Arrays. posortowane</span><span class="sxs-lookup"><span data-stu-id="94a06-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)