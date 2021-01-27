---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850879"
---
# <a name="zip4-function"></a><span data-ttu-id="96c7e-102">Zip4, funkcja</span><span class="sxs-lookup"><span data-stu-id="96c7e-102">Zip4 function</span></span>

<span data-ttu-id="96c7e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="96c7e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="96c7e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="96c7e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="96c7e-105">Zip4 jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="96c7e-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="96c7e-106">Użyj <xref:Microsoft.Quantum.Arrays.Zipped4> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="96c7e-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="96c7e-107">W przypadku czterech tablic funkcja zwraca nową tablicę składającą się z 4 krotek, tak że każda 4-krotka zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="96c7e-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="96c7e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="96c7e-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="96c7e-109">pierwszy: 'T 1 []</span><span class="sxs-lookup"><span data-stu-id="96c7e-109">first : 'T1[]</span></span>

<span data-ttu-id="96c7e-110">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="96c7e-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="96c7e-111">sekundę: brak 2 []</span><span class="sxs-lookup"><span data-stu-id="96c7e-111">second : 'T2[]</span></span>

<span data-ttu-id="96c7e-112">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="96c7e-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="96c7e-113">trzecia: t 3 []</span><span class="sxs-lookup"><span data-stu-id="96c7e-113">third : 'T3[]</span></span>

<span data-ttu-id="96c7e-114">Tablica zawierająca wartości trzeciego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="96c7e-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="96c7e-115">czwarty: t 4 []</span><span class="sxs-lookup"><span data-stu-id="96c7e-115">fourth : 'T4[]</span></span>

<span data-ttu-id="96c7e-116">Tablica zawierająca wartości dla czwartego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="96c7e-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="96c7e-117">Wynik: (t 1, brak 2, t 3, t 4) []</span><span class="sxs-lookup"><span data-stu-id="96c7e-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="96c7e-118">Tablica zawierająca 4-krotek formularza `(first[idx], second[idx], third[idx], fourth[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="96c7e-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="96c7e-119">Jeśli cztery tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="96c7e-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="96c7e-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="96c7e-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="96c7e-121">Brak 1</span><span class="sxs-lookup"><span data-stu-id="96c7e-121">'T1</span></span>

<span data-ttu-id="96c7e-122">Typ pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="96c7e-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="96c7e-123">Brak 2</span><span class="sxs-lookup"><span data-stu-id="96c7e-123">'T2</span></span>

<span data-ttu-id="96c7e-124">Typ drugiego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="96c7e-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="96c7e-125">Brak 3</span><span class="sxs-lookup"><span data-stu-id="96c7e-125">'T3</span></span>

<span data-ttu-id="96c7e-126">Typ trzeciego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="96c7e-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="96c7e-127">T 4</span><span class="sxs-lookup"><span data-stu-id="96c7e-127">'T4</span></span>

<span data-ttu-id="96c7e-128">Typ czwartych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="96c7e-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="96c7e-129">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="96c7e-129">See Also</span></span>

- [<span data-ttu-id="96c7e-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="96c7e-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="96c7e-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="96c7e-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)