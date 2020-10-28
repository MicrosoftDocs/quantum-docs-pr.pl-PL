---
uid: Microsoft.Quantum.Arrays.Swapped
title: Zamieniono funkcję
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: fa5b37b4caf5d8f19ed05075ddd7bc4217036bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718824"
---
# <a name="swapped-function"></a><span data-ttu-id="fbfc4-102">Zamieniono funkcję</span><span class="sxs-lookup"><span data-stu-id="fbfc4-102">Swapped function</span></span>

<span data-ttu-id="fbfc4-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fbfc4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fbfc4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbfc4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbfc4-105">Stosuje wymianę dwóch elementów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fbfc4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fbfc4-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="fbfc4-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbfc4-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbfc4-108">Indeks pierwszego elementu, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="fbfc4-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbfc4-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbfc4-110">Indeks drugiego elementu, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="fbfc4-111">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="fbfc4-111">arr : 'T[]</span></span>

<span data-ttu-id="fbfc4-112">Tablica z elementami, które mają zostać zamienione.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="fbfc4-113">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="fbfc4-113">Output : 'T[]</span></span>

<span data-ttu-id="fbfc4-114">Tablica z zastosowanym zamianą w miejscu.</span><span class="sxs-lookup"><span data-stu-id="fbfc4-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="fbfc4-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="fbfc4-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="fbfc4-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fbfc4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbfc4-117">'C</span><span class="sxs-lookup"><span data-stu-id="fbfc4-117">'T</span></span>

