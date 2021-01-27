---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 —, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845350"
---
# <a name="zip3-function"></a><span data-ttu-id="cb400-102">Zip3 —, funkcja</span><span class="sxs-lookup"><span data-stu-id="cb400-102">Zip3 function</span></span>

<span data-ttu-id="cb400-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cb400-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cb400-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cb400-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="cb400-105">Zip3 — jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="cb400-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="cb400-106">Użyj <xref:Microsoft.Quantum.Arrays.Zipped3> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="cb400-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="cb400-107">Podano trzy tablice, zwraca nową tablicę 3-krotek, tak że każda 3-krotka zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="cb400-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="cb400-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cb400-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="cb400-109">pierwszy: 'T 1 []</span><span class="sxs-lookup"><span data-stu-id="cb400-109">first : 'T1[]</span></span>

<span data-ttu-id="cb400-110">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="cb400-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="cb400-111">sekundę: brak 2 []</span><span class="sxs-lookup"><span data-stu-id="cb400-111">second : 'T2[]</span></span>

<span data-ttu-id="cb400-112">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="cb400-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="cb400-113">trzecia: t 3 []</span><span class="sxs-lookup"><span data-stu-id="cb400-113">third : 'T3[]</span></span>

<span data-ttu-id="cb400-114">Tablica zawierająca wartości trzeciego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="cb400-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="cb400-115">Wynik: (t 1, t 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="cb400-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="cb400-116">Tablica zawierająca 3-krotek formularza `(first[idx], second[idx], third[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="cb400-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="cb400-117">Jeśli trzy tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="cb400-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="cb400-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cb400-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="cb400-119">Brak 1</span><span class="sxs-lookup"><span data-stu-id="cb400-119">'T1</span></span>

<span data-ttu-id="cb400-120">Typ pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="cb400-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="cb400-121">Brak 2</span><span class="sxs-lookup"><span data-stu-id="cb400-121">'T2</span></span>

<span data-ttu-id="cb400-122">Typ drugiego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="cb400-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="cb400-123">Brak 3</span><span class="sxs-lookup"><span data-stu-id="cb400-123">'T3</span></span>

<span data-ttu-id="cb400-124">Typ trzeciego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="cb400-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb400-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cb400-125">See Also</span></span>

- [<span data-ttu-id="cb400-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="cb400-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="cb400-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="cb400-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)