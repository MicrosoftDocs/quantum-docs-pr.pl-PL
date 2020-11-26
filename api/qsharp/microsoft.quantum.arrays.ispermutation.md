---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermutacja — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220930"
---
# <a name="ispermutation-function"></a><span data-ttu-id="4d43e-102">Ispermutacja — funkcja</span><span class="sxs-lookup"><span data-stu-id="4d43e-102">IsPermutation function</span></span>

<span data-ttu-id="4d43e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4d43e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4d43e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d43e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d43e-105">Zwraca wartość PRAWDA, jeśli i tylko wtedy, gdy dana tablica reprezentuje permutację.</span><span class="sxs-lookup"><span data-stu-id="4d43e-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="4d43e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4d43e-106">Description</span></span>

<span data-ttu-id="4d43e-107">Dana tablica `array` o długości `n` zwraca wartość PRAWDA, jeśli i tylko wtedy, gdy każda liczba całkowita z `0` ma `n - 1` być wyświetlana dokładnie raz w `array` , na przykład, która `array` może być interpretowana jako Permutacja dla `n` elementów.</span><span class="sxs-lookup"><span data-stu-id="4d43e-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="4d43e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4d43e-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="4d43e-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4d43e-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4d43e-110">Tablica, która może lub nie może reprezentować permutacji.</span><span class="sxs-lookup"><span data-stu-id="4d43e-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4d43e-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d43e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d43e-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4d43e-112">Remarks</span></span>

<span data-ttu-id="4d43e-113">Tablica o długości zero jest prosta permutacji.</span><span class="sxs-lookup"><span data-stu-id="4d43e-113">An array of length zero is trivially a permutation.</span></span>