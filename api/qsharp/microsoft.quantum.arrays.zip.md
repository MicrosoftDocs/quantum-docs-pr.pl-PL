---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718728"
---
# <a name="zip-function"></a><span data-ttu-id="1602b-102">Zip — funkcja</span><span class="sxs-lookup"><span data-stu-id="1602b-102">Zip function</span></span>

<span data-ttu-id="1602b-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1602b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1602b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1602b-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="1602b-105">Plik zip został uznany za przestarzały.</span><span class="sxs-lookup"><span data-stu-id="1602b-105">Zip has been deprecated.</span></span> <span data-ttu-id="1602b-106">Użyj <xref:Microsoft.Quantum.Arrays.Zipped> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="1602b-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="1602b-107">Dana dwie tablice zwraca nową tablicę par, w taki sposób, że każda para zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="1602b-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="1602b-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1602b-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="1602b-109">Left: t []</span><span class="sxs-lookup"><span data-stu-id="1602b-109">left : 'T[]</span></span>

<span data-ttu-id="1602b-110">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="1602b-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="1602b-111">prawy: "U []</span><span class="sxs-lookup"><span data-stu-id="1602b-111">right : 'U[]</span></span>

<span data-ttu-id="1602b-112">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="1602b-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="1602b-113">Wynik: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="1602b-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="1602b-114">Tablica zawierająca pary formularzy `(left[idx], right[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="1602b-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="1602b-115">Jeśli dwie tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="1602b-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1602b-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1602b-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1602b-117">'C</span><span class="sxs-lookup"><span data-stu-id="1602b-117">'T</span></span>

<span data-ttu-id="1602b-118">Typ elementów tablicy po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="1602b-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="1602b-119">' U</span><span class="sxs-lookup"><span data-stu-id="1602b-119">'U</span></span>

<span data-ttu-id="1602b-120">Typ odpowiednich elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="1602b-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="1602b-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1602b-121">See Also</span></span>

- [<span data-ttu-id="1602b-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="1602b-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="1602b-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="1602b-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="1602b-124">Microsoft. Quantum. Arrays. unspakowane</span><span class="sxs-lookup"><span data-stu-id="1602b-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)