---
uid: Microsoft.Quantum.Arrays.All
title: All — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 17e61ea161b90fe089b7df7c10188d604d72dcfa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842895"
---
# <a name="all-function"></a><span data-ttu-id="be354-102">All — funkcja</span><span class="sxs-lookup"><span data-stu-id="be354-102">All function</span></span>

<span data-ttu-id="be354-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="be354-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="be354-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be354-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be354-105">Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, i sprawdza, czy wszystkie elementy tablicy spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="be354-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="be354-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="be354-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="be354-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="be354-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="be354-108">Funkcja z `'T` do `Bool` , która jest używana do sprawdzania elementów.</span><span class="sxs-lookup"><span data-stu-id="be354-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="be354-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="be354-109">array : 'T[]</span></span>

<span data-ttu-id="be354-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="be354-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="be354-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="be354-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="be354-112">`Bool`Wartość i funkcji predykatu zastosowana do wszystkich elementów.</span><span class="sxs-lookup"><span data-stu-id="be354-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="be354-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="be354-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be354-114">'C</span><span class="sxs-lookup"><span data-stu-id="be354-114">'T</span></span>

<span data-ttu-id="be354-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="be354-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="be354-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="be354-116">Example</span></span>

<span data-ttu-id="be354-117">Poniższy kod sprawdza, czy wszystkie elementy tablicy są inne niż zero:</span><span class="sxs-lookup"><span data-stu-id="be354-117">The following code checks whether all elements of the array are non-zero:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function AllDemo() : Unit {
    let predicate = NotEqualI(_, 0);
    let isNonZero = All(predicate, [2, 3, 4, 5, 6, 0]);
    Message($"{isNonZero}");
}
```

## <a name="remarks"></a><span data-ttu-id="be354-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="be354-118">Remarks</span></span>

<span data-ttu-id="be354-119">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i funkcję `predicate: 'T -> Bool` możemy utworzyć `Bool` wartość wskazującą, czy wszystkie elementy są spełnione `predicate` .</span><span class="sxs-lookup"><span data-stu-id="be354-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>