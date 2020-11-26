---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funkcja IsSorted
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220839"
---
# <a name="issorted-function"></a><span data-ttu-id="45603-102">Funkcja IsSorted</span><span class="sxs-lookup"><span data-stu-id="45603-102">IsSorted function</span></span>

<span data-ttu-id="45603-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="45603-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="45603-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="45603-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="45603-105">Dana tablica zwraca czy tablica jest sortowana zgodnie z definicją przez daną funkcję porównania.</span><span class="sxs-lookup"><span data-stu-id="45603-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="45603-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="45603-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="45603-107">Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="45603-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="45603-108">Funkcja, która porównuje dwa elementy, które `a` są uważane za mniej niż lub równą `b` if `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="45603-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="45603-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="45603-109">array : 'T[]</span></span>

<span data-ttu-id="45603-110">Tablica, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="45603-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="45603-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="45603-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="45603-112">`true` Jeśli i tylko wtedy, gdy dla każdej pary `a` elementów `b` i `array` występuje w tej kolejności, `comparison(a, b)` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="45603-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="45603-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="45603-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="45603-114">'C</span><span class="sxs-lookup"><span data-stu-id="45603-114">'T</span></span>

<span data-ttu-id="45603-115">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="45603-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="45603-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="45603-116">Remarks</span></span>

<span data-ttu-id="45603-117">Przyjmuje się `comparison` , że funkcja jest przechodnia, na przykład jeśli `comparison(a, b)` i `comparison(b, c)` , `comparison(a, c)` jest przyjmowana.</span><span class="sxs-lookup"><span data-stu-id="45603-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="45603-118">Jeśli ta właściwość nie jest wstrzymana, dane wyjściowe tej funkcji mogą być nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="45603-118">If this property does not hold, then the output of this function may be incorrect.</span></span>