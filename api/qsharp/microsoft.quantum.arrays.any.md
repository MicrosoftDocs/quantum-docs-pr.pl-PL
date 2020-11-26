---
uid: Microsoft.Quantum.Arrays.Any
title: Dowolna funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: 717ab9ebcbb864a6faf1c14cd36125e589849f2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221661"
---
# <a name="any-function"></a><span data-ttu-id="a7ef1-102">Dowolna funkcja</span><span class="sxs-lookup"><span data-stu-id="a7ef1-102">Any function</span></span>

<span data-ttu-id="a7ef1-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a7ef1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a7ef1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a7ef1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a7ef1-105">Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, sprawdza, czy co najmniej jeden element tablicy spełnia predykat.</span><span class="sxs-lookup"><span data-stu-id="a7ef1-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="a7ef1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a7ef1-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="a7ef1-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7ef1-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7ef1-108">Funkcja z `'T` do `Bool` , która jest używana do sprawdzania elementów.</span><span class="sxs-lookup"><span data-stu-id="a7ef1-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="a7ef1-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="a7ef1-109">array : 'T[]</span></span>

<span data-ttu-id="a7ef1-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="a7ef1-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a7ef1-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a7ef1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a7ef1-112">`Bool`Wartość lub funkcji predykatu zastosowana do wszystkich elementów.</span><span class="sxs-lookup"><span data-stu-id="a7ef1-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a7ef1-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a7ef1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a7ef1-114">'C</span><span class="sxs-lookup"><span data-stu-id="a7ef1-114">'T</span></span>

<span data-ttu-id="a7ef1-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="a7ef1-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7ef1-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a7ef1-116">Remarks</span></span>

<span data-ttu-id="a7ef1-117">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i funkcję `predicate: 'T -> Bool` możemy utworzyć `Bool` wartość wskazującą, czy jakiś element spełnia `predicate` .</span><span class="sxs-lookup"><span data-stu-id="a7ef1-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>