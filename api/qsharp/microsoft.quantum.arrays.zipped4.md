---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: e932cd4c266b39a3a88da48e649448d0028f61e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845329"
---
# <a name="zipped4-function"></a><span data-ttu-id="21781-102">Zipped4, funkcja</span><span class="sxs-lookup"><span data-stu-id="21781-102">Zipped4 function</span></span>

<span data-ttu-id="21781-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="21781-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="21781-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="21781-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="21781-105">W przypadku czterech tablic funkcja zwraca nową tablicę składającą się z 4 krotek, tak że każda 4-krotka zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="21781-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="21781-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="21781-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="21781-107">pierwszy: 'T 1 []</span><span class="sxs-lookup"><span data-stu-id="21781-107">first : 'T1[]</span></span>

<span data-ttu-id="21781-108">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="21781-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="21781-109">sekundę: brak 2 []</span><span class="sxs-lookup"><span data-stu-id="21781-109">second : 'T2[]</span></span>

<span data-ttu-id="21781-110">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="21781-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="21781-111">trzecia: t 3 []</span><span class="sxs-lookup"><span data-stu-id="21781-111">third : 'T3[]</span></span>

<span data-ttu-id="21781-112">Tablica zawierająca wartości trzeciego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="21781-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="21781-113">czwarty: t 4 []</span><span class="sxs-lookup"><span data-stu-id="21781-113">fourth : 'T4[]</span></span>

<span data-ttu-id="21781-114">Tablica zawierająca wartości dla czwartego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="21781-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="21781-115">Wynik: (t 1, brak 2, t 3, t 4) []</span><span class="sxs-lookup"><span data-stu-id="21781-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="21781-116">Tablica zawierająca 4-krotek formularza `(first[idx], second[idx], third[idx], fourth[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="21781-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="21781-117">Jeśli cztery tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="21781-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="21781-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="21781-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="21781-119">Brak 1</span><span class="sxs-lookup"><span data-stu-id="21781-119">'T1</span></span>

<span data-ttu-id="21781-120">Typ pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="21781-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="21781-121">Brak 2</span><span class="sxs-lookup"><span data-stu-id="21781-121">'T2</span></span>

<span data-ttu-id="21781-122">Typ drugiego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="21781-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="21781-123">Brak 3</span><span class="sxs-lookup"><span data-stu-id="21781-123">'T3</span></span>

<span data-ttu-id="21781-124">Typ trzeciego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="21781-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="21781-125">T 4</span><span class="sxs-lookup"><span data-stu-id="21781-125">'T4</span></span>

<span data-ttu-id="21781-126">Typ czwartych elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="21781-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="21781-127">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="21781-127">See Also</span></span>

- [<span data-ttu-id="21781-128">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="21781-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="21781-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="21781-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)