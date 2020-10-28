---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: c0535ca4d6e0de13bf809a21e69d100dcb798d1f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718692"
---
# <a name="zipped3-function"></a><span data-ttu-id="9eee5-102">Zipped3, funkcja</span><span class="sxs-lookup"><span data-stu-id="9eee5-102">Zipped3 function</span></span>

<span data-ttu-id="9eee5-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9eee5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9eee5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9eee5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9eee5-105">Podano trzy tablice, zwraca nową tablicę 3-krotek, tak że każda 3-krotka zawiera element z każdej oryginalnej tablicy.</span><span class="sxs-lookup"><span data-stu-id="9eee5-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="9eee5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9eee5-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="9eee5-107">pierwszy: 'T 1 []</span><span class="sxs-lookup"><span data-stu-id="9eee5-107">first : 'T1[]</span></span>

<span data-ttu-id="9eee5-108">Tablica zawierająca wartości dla pierwszego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="9eee5-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="9eee5-109">sekundę: brak 2 []</span><span class="sxs-lookup"><span data-stu-id="9eee5-109">second : 'T2[]</span></span>

<span data-ttu-id="9eee5-110">Tablica zawierająca wartości dla drugiego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="9eee5-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="9eee5-111">trzecia: t 3 []</span><span class="sxs-lookup"><span data-stu-id="9eee5-111">third : 'T3[]</span></span>

<span data-ttu-id="9eee5-112">Tablica zawierająca wartości trzeciego elementu każdej krotki.</span><span class="sxs-lookup"><span data-stu-id="9eee5-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="9eee5-113">Wynik: (t 1, t 2, t 3) []</span><span class="sxs-lookup"><span data-stu-id="9eee5-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="9eee5-114">Tablica zawierająca 3-krotek formularza `(first[idx], second[idx], third[idx])` dla każdej z nich `idx` .</span><span class="sxs-lookup"><span data-stu-id="9eee5-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="9eee5-115">Jeśli trzy tablice nie mają równej długości, dane wyjściowe będą tak długo jak krótsze dane wejściowe.</span><span class="sxs-lookup"><span data-stu-id="9eee5-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9eee5-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9eee5-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="9eee5-117">Brak 1</span><span class="sxs-lookup"><span data-stu-id="9eee5-117">'T1</span></span>

<span data-ttu-id="9eee5-118">Typ pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9eee5-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="9eee5-119">Brak 2</span><span class="sxs-lookup"><span data-stu-id="9eee5-119">'T2</span></span>

<span data-ttu-id="9eee5-120">Typ drugiego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9eee5-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="9eee5-121">Brak 3</span><span class="sxs-lookup"><span data-stu-id="9eee5-121">'T3</span></span>

<span data-ttu-id="9eee5-122">Typ trzeciego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9eee5-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="9eee5-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9eee5-123">See Also</span></span>

- [<span data-ttu-id="9eee5-124">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="9eee5-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="9eee5-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="9eee5-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)