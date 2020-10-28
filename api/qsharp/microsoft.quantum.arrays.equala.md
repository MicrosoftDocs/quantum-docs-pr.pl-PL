---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equal — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719289"
---
# <a name="equala-function"></a><span data-ttu-id="096fe-102">Equal — funkcja</span><span class="sxs-lookup"><span data-stu-id="096fe-102">EqualA function</span></span>

<span data-ttu-id="096fe-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="096fe-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="096fe-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="096fe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="096fe-105">Dana dwie tablice tego samego typu i predykatu, który jest zdefiniowany dla par elementów tablic, sprawdza, czy tablice są równe.</span><span class="sxs-lookup"><span data-stu-id="096fe-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="096fe-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="096fe-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="096fe-107">równe: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="096fe-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="096fe-108">Funkcja z krotki `('T, 'T)` do `Bool` , która służy do sprawdzania, czy dwa elementy tablic są równe.</span><span class="sxs-lookup"><span data-stu-id="096fe-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="096fe-109">tablica1: 'T []</span><span class="sxs-lookup"><span data-stu-id="096fe-109">array1 : 'T[]</span></span>

<span data-ttu-id="096fe-110">Pierwsza tablica do porównania.</span><span class="sxs-lookup"><span data-stu-id="096fe-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="096fe-111">tablica2: t []</span><span class="sxs-lookup"><span data-stu-id="096fe-111">array2 : 'T[]</span></span>

<span data-ttu-id="096fe-112">Druga tablica do porównania.</span><span class="sxs-lookup"><span data-stu-id="096fe-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="096fe-113">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="096fe-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="096fe-114">Wartość `true` Jeśli i tylko wtedy `array1` , gdy i `array2` są równe.</span><span class="sxs-lookup"><span data-stu-id="096fe-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="096fe-115">Oznacza to, że jeśli obie tablice mają tę samą długość, a wszystkie elementy są równe zdefiniowane przez `equal` .</span><span class="sxs-lookup"><span data-stu-id="096fe-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="096fe-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="096fe-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="096fe-117">'C</span><span class="sxs-lookup"><span data-stu-id="096fe-117">'T</span></span>

<span data-ttu-id="096fe-118">Typ elementów każdej tablicy.</span><span class="sxs-lookup"><span data-stu-id="096fe-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="096fe-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="096fe-119">Remarks</span></span>

<span data-ttu-id="096fe-120">Ta funkcja jest definiowana dla typów ogólnych; oznacza to, że za każdym razem, gdy mamy dwie tablice `'T[]` i funkcję `equal: ('T, 'T) -> Bool` , ta funkcja zwraca `Bool` wartość wskazującą, czy tablice są równe.</span><span class="sxs-lookup"><span data-stu-id="096fe-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="096fe-121">W przypadku dwóch tablic, które mają być uznawane za równe, muszą one mieć równą długość i elementy w tych samych położeniach w tablicach muszą być równe.</span><span class="sxs-lookup"><span data-stu-id="096fe-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>