---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: Ispermutacja — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848091"
---
# <a name="ispermutation-function"></a><span data-ttu-id="150e8-102">Ispermutacja — funkcja</span><span class="sxs-lookup"><span data-stu-id="150e8-102">IsPermutation function</span></span>

<span data-ttu-id="150e8-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="150e8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="150e8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="150e8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="150e8-105">Zwraca wartość PRAWDA, jeśli i tylko wtedy, gdy dana tablica reprezentuje permutację.</span><span class="sxs-lookup"><span data-stu-id="150e8-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="150e8-106">Opis</span><span class="sxs-lookup"><span data-stu-id="150e8-106">Description</span></span>

<span data-ttu-id="150e8-107">Dana tablica `array` o długości `n` zwraca wartość PRAWDA, jeśli i tylko wtedy, gdy każda liczba całkowita z `0` ma `n - 1` być wyświetlana dokładnie raz w `array` , na przykład, która `array` może być interpretowana jako Permutacja dla `n` elementów.</span><span class="sxs-lookup"><span data-stu-id="150e8-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="150e8-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="150e8-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="150e8-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="150e8-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="150e8-110">Tablica, która może lub nie może reprezentować permutacji.</span><span class="sxs-lookup"><span data-stu-id="150e8-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="150e8-111">Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="150e8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="150e8-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="150e8-112">Example</span></span>

<span data-ttu-id="150e8-113">Poniższy kod Q # drukuje komunikat "cała Diagnostyka została ukończona pomyślnie":</span><span class="sxs-lookup"><span data-stu-id="150e8-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="150e8-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="150e8-114">Remarks</span></span>

<span data-ttu-id="150e8-115">Tablica o długości zero jest prosta permutacji.</span><span class="sxs-lookup"><span data-stu-id="150e8-115">An array of length zero is trivially a permutation.</span></span>