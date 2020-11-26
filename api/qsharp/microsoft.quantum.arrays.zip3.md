---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3 —, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: a6e7519755c4d473f6ba255ac5f877b2a3894d71
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219825"
---
# <a name="zip3-function"></a><span data-ttu-id="b5282-102">Zip3 —, funkcja</span><span class="sxs-lookup"><span data-stu-id="b5282-102">Zip3 function</span></span>

<span data-ttu-id="b5282-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b5282-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b5282-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5282-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="b5282-105">Zip3 — jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="b5282-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="b5282-106">Użyj <xref:Microsoft.Quantum.Arrays.Zipped3> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="b5282-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="b5282-107">Podano trzy tablice, zwraca nową tablicę 3-krotek, tak że każda 3-krotka zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5282-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="b5282-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5282-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="b5282-109">pierwszy: 'T 1 []</span><span class="sxs-lookup"><span data-stu-id="b5282-109">first : 'T1[]</span></span>

<span data-ttu-id="b5282-110">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="b5282-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="b5282-111">sekundę: brak 2 []</span><span class="sxs-lookup"><span data-stu-id="b5282-111">second : 'T2[]</span></span>

<span data-ttu-id="b5282-112">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="b5282-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="b5282-113">trzecia: t 3 []</span><span class="sxs-lookup"><span data-stu-id="b5282-113">third : 'T3[]</span></span>

<span data-ttu-id="b5282-114">Tablica zawierająca wartości trzeciego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="b5282-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="b5282-115">Wynik: (t 1, t 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="b5282-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="b5282-116">Tablica zawierająca 3-krotek formularza `(first[idx], second[idx], third[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="b5282-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="b5282-117">Jeśli trzy tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="b5282-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b5282-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b5282-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="b5282-119">Brak 1</span><span class="sxs-lookup"><span data-stu-id="b5282-119">'T1</span></span>

<span data-ttu-id="b5282-120">Typ pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5282-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="b5282-121">Brak 2</span><span class="sxs-lookup"><span data-stu-id="b5282-121">'T2</span></span>

<span data-ttu-id="b5282-122">Typ drugiego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5282-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="b5282-123">Brak 3</span><span class="sxs-lookup"><span data-stu-id="b5282-123">'T3</span></span>

<span data-ttu-id="b5282-124">Typ trzeciego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5282-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5282-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5282-125">See Also</span></span>

- [<span data-ttu-id="b5282-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="b5282-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="b5282-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="b5282-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)