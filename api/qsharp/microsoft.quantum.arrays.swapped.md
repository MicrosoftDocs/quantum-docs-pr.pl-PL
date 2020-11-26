---
uid: Microsoft.Quantum.Arrays.Swapped
title: Zamieniono funkcję
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220131"
---
# <a name="swapped-function"></a><span data-ttu-id="196b2-102">Zamieniono funkcję</span><span class="sxs-lookup"><span data-stu-id="196b2-102">Swapped function</span></span>

<span data-ttu-id="196b2-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="196b2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="196b2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="196b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="196b2-105">Stosuje wymianę dwóch elementów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="196b2-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="196b2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="196b2-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="196b2-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="196b2-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="196b2-108">Indeks pierwszego elementu, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="196b2-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="196b2-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="196b2-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="196b2-110">Indeks drugiego elementu, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="196b2-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="196b2-111">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="196b2-111">arr : 'T[]</span></span>

<span data-ttu-id="196b2-112">Tablica z elementami, które mają zostać zamienione.</span><span class="sxs-lookup"><span data-stu-id="196b2-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="196b2-113">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="196b2-113">Output : 'T[]</span></span>

<span data-ttu-id="196b2-114">Tablica z zastosowanym zamianą w miejscu.</span><span class="sxs-lookup"><span data-stu-id="196b2-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="196b2-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="196b2-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="196b2-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="196b2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="196b2-117">'C</span><span class="sxs-lookup"><span data-stu-id="196b2-117">'T</span></span>

