---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkcja spakowane
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845348"
---
# <a name="zipped-function"></a><span data-ttu-id="b5d9b-102">Funkcja spakowane</span><span class="sxs-lookup"><span data-stu-id="b5d9b-102">Zipped function</span></span>

<span data-ttu-id="b5d9b-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b5d9b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b5d9b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5d9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5d9b-105">Dana dwie tablice zwraca nową tablicę par, w taki sposób, że każda para zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5d9b-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="b5d9b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5d9b-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="b5d9b-107">Left: t []</span><span class="sxs-lookup"><span data-stu-id="b5d9b-107">left : 'T[]</span></span>

<span data-ttu-id="b5d9b-108">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="b5d9b-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="b5d9b-109">prawy: "U []</span><span class="sxs-lookup"><span data-stu-id="b5d9b-109">right : 'U[]</span></span>

<span data-ttu-id="b5d9b-110">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="b5d9b-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="b5d9b-111">Wynik: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="b5d9b-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="b5d9b-112">Tablica zawierająca pary formularzy `(left[idx], right[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="b5d9b-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="b5d9b-113">Jeśli dwie tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="b5d9b-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b5d9b-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b5d9b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5d9b-115">'C</span><span class="sxs-lookup"><span data-stu-id="b5d9b-115">'T</span></span>

<span data-ttu-id="b5d9b-116">Typ elementów tablicy po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="b5d9b-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="b5d9b-117">' U</span><span class="sxs-lookup"><span data-stu-id="b5d9b-117">'U</span></span>

<span data-ttu-id="b5d9b-118">Typ odpowiednich elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5d9b-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="b5d9b-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="b5d9b-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="b5d9b-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5d9b-120">See Also</span></span>

- [<span data-ttu-id="b5d9b-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="b5d9b-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="b5d9b-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="b5d9b-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="b5d9b-123">Microsoft. Quantum. Arrays. unspakowane</span><span class="sxs-lookup"><span data-stu-id="b5d9b-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)