---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funkcja IsSorted
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845740"
---
# <a name="issorted-function"></a><span data-ttu-id="2ca96-102">Funkcja IsSorted</span><span class="sxs-lookup"><span data-stu-id="2ca96-102">IsSorted function</span></span>

<span data-ttu-id="2ca96-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2ca96-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2ca96-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ca96-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ca96-105">Dana tablica zwraca czy tablica jest sortowana zgodnie z definicją przez daną funkcję porównania.</span><span class="sxs-lookup"><span data-stu-id="2ca96-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="2ca96-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2ca96-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="2ca96-107">Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2ca96-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2ca96-108">Funkcja, która porównuje dwa elementy, które `a` są uważane za mniej niż lub równą `b` if `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="2ca96-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="2ca96-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="2ca96-109">array : 'T[]</span></span>

<span data-ttu-id="2ca96-110">Tablica, która ma zostać sprawdzona.</span><span class="sxs-lookup"><span data-stu-id="2ca96-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="2ca96-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="2ca96-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="2ca96-112">`true` Jeśli i tylko wtedy, gdy dla każdej pary `a` elementów `b` i `array` występuje w tej kolejności, `comparison(a, b)` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="2ca96-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2ca96-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2ca96-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2ca96-114">'C</span><span class="sxs-lookup"><span data-stu-id="2ca96-114">'T</span></span>

<span data-ttu-id="2ca96-115">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="2ca96-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="2ca96-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2ca96-116">Remarks</span></span>

<span data-ttu-id="2ca96-117">Przyjmuje się `comparison` , że funkcja jest przechodnia, na przykład jeśli `comparison(a, b)` i `comparison(b, c)` , `comparison(a, c)` jest przyjmowana.</span><span class="sxs-lookup"><span data-stu-id="2ca96-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="2ca96-118">Jeśli ta właściwość nie jest wstrzymana, dane wyjściowe tej funkcji mogą być nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="2ca96-118">If this property does not hold, then the output of this function may be incorrect.</span></span>