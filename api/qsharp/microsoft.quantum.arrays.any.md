---
uid: Microsoft.Quantum.Arrays.Any
title: Dowolna funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719472"
---
# <a name="any-function"></a><span data-ttu-id="6787d-102">Dowolna funkcja</span><span class="sxs-lookup"><span data-stu-id="6787d-102">Any function</span></span>

<span data-ttu-id="6787d-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6787d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6787d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6787d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6787d-105">Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, sprawdza, czy co najmniej jeden element tablicy spełnia predykat.</span><span class="sxs-lookup"><span data-stu-id="6787d-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="6787d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6787d-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="6787d-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6787d-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6787d-108">Funkcja z `'T` do `Bool` , która jest używana do sprawdzania elementów.</span><span class="sxs-lookup"><span data-stu-id="6787d-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="6787d-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="6787d-109">array : 'T[]</span></span>

<span data-ttu-id="6787d-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="6787d-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6787d-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6787d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6787d-112">`Bool`Wartość lub funkcji predykatu zastosowana do wszystkich elementów.</span><span class="sxs-lookup"><span data-stu-id="6787d-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6787d-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6787d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6787d-114">'C</span><span class="sxs-lookup"><span data-stu-id="6787d-114">'T</span></span>

<span data-ttu-id="6787d-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="6787d-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="6787d-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6787d-116">Remarks</span></span>

<span data-ttu-id="6787d-117">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i funkcję `predicate: 'T -> Bool` możemy utworzyć `Bool` wartość wskazującą, czy jakiś element spełnia `predicate` .</span><span class="sxs-lookup"><span data-stu-id="6787d-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>