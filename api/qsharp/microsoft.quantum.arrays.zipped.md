---
uid: Microsoft.Quantum.Arrays.Zipped
title: Funkcja spakowane
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219757"
---
# <a name="zipped-function"></a><span data-ttu-id="77f99-102">Funkcja spakowane</span><span class="sxs-lookup"><span data-stu-id="77f99-102">Zipped function</span></span>

<span data-ttu-id="77f99-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="77f99-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="77f99-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77f99-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77f99-105">Dana dwie tablice zwraca nową tablicę par, w taki sposób, że każda para zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="77f99-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="77f99-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="77f99-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="77f99-107">Left: t []</span><span class="sxs-lookup"><span data-stu-id="77f99-107">left : 'T[]</span></span>

<span data-ttu-id="77f99-108">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="77f99-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="77f99-109">prawy: "U []</span><span class="sxs-lookup"><span data-stu-id="77f99-109">right : 'U[]</span></span>

<span data-ttu-id="77f99-110">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="77f99-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="77f99-111">Wynik: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="77f99-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="77f99-112">Tablica zawierająca pary formularzy `(left[idx], right[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="77f99-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="77f99-113">Jeśli dwie tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="77f99-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="77f99-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="77f99-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77f99-115">'C</span><span class="sxs-lookup"><span data-stu-id="77f99-115">'T</span></span>

<span data-ttu-id="77f99-116">Typ elementów tablicy po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="77f99-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="77f99-117">' U</span><span class="sxs-lookup"><span data-stu-id="77f99-117">'U</span></span>

<span data-ttu-id="77f99-118">Typ odpowiednich elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="77f99-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="77f99-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="77f99-119">See Also</span></span>

- [<span data-ttu-id="77f99-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="77f99-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="77f99-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="77f99-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="77f99-122">Microsoft. Quantum. Arrays. unspakowane</span><span class="sxs-lookup"><span data-stu-id="77f99-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)