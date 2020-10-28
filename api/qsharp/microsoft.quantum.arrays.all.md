---
uid: Microsoft.Quantum.Arrays.All
title: All — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719481"
---
# <a name="all-function"></a><span data-ttu-id="8d302-102">All — funkcja</span><span class="sxs-lookup"><span data-stu-id="8d302-102">All function</span></span>

<span data-ttu-id="8d302-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8d302-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8d302-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8d302-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8d302-105">Dana tablica i predykat, który jest zdefiniowany dla elementów tablicy, i sprawdza, czy wszystkie elementy tablicy spełniają predykat.</span><span class="sxs-lookup"><span data-stu-id="8d302-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="8d302-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8d302-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="8d302-107">predykat: > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8d302-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8d302-108">Funkcja z `'T` do `Bool` , która jest używana do sprawdzania elementów.</span><span class="sxs-lookup"><span data-stu-id="8d302-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="8d302-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="8d302-109">array : 'T[]</span></span>

<span data-ttu-id="8d302-110">Tablica elementów `'T` .</span><span class="sxs-lookup"><span data-stu-id="8d302-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8d302-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8d302-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8d302-112">`Bool`Wartość i funkcji predykatu zastosowana do wszystkich elementów.</span><span class="sxs-lookup"><span data-stu-id="8d302-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8d302-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8d302-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8d302-114">'C</span><span class="sxs-lookup"><span data-stu-id="8d302-114">'T</span></span>

<span data-ttu-id="8d302-115">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="8d302-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d302-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8d302-116">Remarks</span></span>

<span data-ttu-id="8d302-117">Funkcja jest definiowana dla typów ogólnych, tzn. zawsze, gdy mamy tablicę `'T[]` i funkcję `predicate: 'T -> Bool` możemy utworzyć `Bool` wartość wskazującą, czy wszystkie elementy są spełnione `predicate` .</span><span class="sxs-lookup"><span data-stu-id="8d302-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>