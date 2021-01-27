---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equal — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848687"
---
# <a name="equala-function"></a><span data-ttu-id="d4bbc-102">Equal — funkcja</span><span class="sxs-lookup"><span data-stu-id="d4bbc-102">EqualA function</span></span>

<span data-ttu-id="d4bbc-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d4bbc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d4bbc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4bbc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4bbc-105">Dana dwie tablice tego samego typu i predykatu, który jest zdefiniowany dla par elementów tablic, sprawdza, czy tablice są równe.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="d4bbc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d4bbc-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="d4bbc-107">równe: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d4bbc-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d4bbc-108">Funkcja z krotki `('T, 'T)` do `Bool` , która służy do sprawdzania, czy dwa elementy tablic są równe.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="d4bbc-109">tablica1: 'T []</span><span class="sxs-lookup"><span data-stu-id="d4bbc-109">array1 : 'T[]</span></span>

<span data-ttu-id="d4bbc-110">Pierwsza tablica do porównania.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="d4bbc-111">tablica2: t []</span><span class="sxs-lookup"><span data-stu-id="d4bbc-111">array2 : 'T[]</span></span>

<span data-ttu-id="d4bbc-112">Druga tablica do porównania.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d4bbc-113">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d4bbc-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d4bbc-114">Wartość `true` Jeśli i tylko wtedy `array1` , gdy i `array2` są równe.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="d4bbc-115">Oznacza to, że jeśli obie tablice mają tę samą długość, a wszystkie elementy są równe zdefiniowane przez `equal` .</span><span class="sxs-lookup"><span data-stu-id="d4bbc-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d4bbc-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d4bbc-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d4bbc-117">'C</span><span class="sxs-lookup"><span data-stu-id="d4bbc-117">'T</span></span>

<span data-ttu-id="d4bbc-118">Typ elementów każdej tablicy.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="d4bbc-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="d4bbc-119">Example</span></span>

<span data-ttu-id="d4bbc-120">Poniższy kod sprawdza, czy różne pary tablic są równe:</span><span class="sxs-lookup"><span data-stu-id="d4bbc-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="d4bbc-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d4bbc-121">Remarks</span></span>

<span data-ttu-id="d4bbc-122">Ta funkcja jest definiowana dla typów ogólnych; oznacza to, że za każdym razem, gdy mamy dwie tablice `'T[]` i funkcję `equal: ('T, 'T) -> Bool` , ta funkcja zwraca `Bool` wartość wskazującą, czy tablice są równe.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="d4bbc-123">W przypadku dwóch tablic, które mają być uznawane za równe, muszą one mieć równą długość i elementy w tych samych położeniach w tablicach muszą być równe.</span><span class="sxs-lookup"><span data-stu-id="d4bbc-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>