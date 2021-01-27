---
uid: Microsoft.Quantum.Arrays.Swapped
title: Zamieniono funkcję
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850949"
---
# <a name="swapped-function"></a><span data-ttu-id="951c0-102">Zamieniono funkcję</span><span class="sxs-lookup"><span data-stu-id="951c0-102">Swapped function</span></span>

<span data-ttu-id="951c0-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="951c0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="951c0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="951c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="951c0-105">Stosuje wymianę dwóch elementów w tablicy.</span><span class="sxs-lookup"><span data-stu-id="951c0-105">Applies a swap of two elements in an array.</span></span>

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="951c0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="951c0-106">Input</span></span>

### <a name="firstindex--int"></a><span data-ttu-id="951c0-107">firstIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="951c0-107">firstIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="951c0-108">Indeks pierwszego elementu, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="951c0-108">Index of the first element to be swapped.</span></span>


### <a name="secondindex--int"></a><span data-ttu-id="951c0-109">secondIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="951c0-109">secondIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="951c0-110">Indeks drugiego elementu, który ma zostać zamieniony.</span><span class="sxs-lookup"><span data-stu-id="951c0-110">Index of the second element to be swapped.</span></span>


### <a name="arr--t"></a><span data-ttu-id="951c0-111">ARR: t []</span><span class="sxs-lookup"><span data-stu-id="951c0-111">arr : 'T[]</span></span>

<span data-ttu-id="951c0-112">Tablica z elementami, które mają zostać zamienione.</span><span class="sxs-lookup"><span data-stu-id="951c0-112">Array with elements to be swapped.</span></span>



## <a name="output--t"></a><span data-ttu-id="951c0-113">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="951c0-113">Output : 'T[]</span></span>

<span data-ttu-id="951c0-114">Tablica z zastosowanym zamianą w miejscu.</span><span class="sxs-lookup"><span data-stu-id="951c0-114">The array with the in place swap applied.</span></span>

## <a name="example"></a><span data-ttu-id="951c0-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="951c0-115">Example</span></span>

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a><span data-ttu-id="951c0-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="951c0-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="951c0-117">'C</span><span class="sxs-lookup"><span data-stu-id="951c0-117">'T</span></span>

