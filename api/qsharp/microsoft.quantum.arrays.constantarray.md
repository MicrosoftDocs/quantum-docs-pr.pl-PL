---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: a3ad8a18856888a0ca6f9dd691242156b0c044d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846220"
---
# <a name="constantarray-function"></a><span data-ttu-id="e8631-102">ConstantArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="e8631-102">ConstantArray function</span></span>

<span data-ttu-id="e8631-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8631-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8631-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e8631-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e8631-105">Tworzy tablicę o podaną długość ze wszystkimi elementami równymi podaną wartością.</span><span class="sxs-lookup"><span data-stu-id="e8631-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e8631-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e8631-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="e8631-107">Długość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8631-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8631-108">Długość nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="e8631-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="e8631-109">wartość: 'T</span><span class="sxs-lookup"><span data-stu-id="e8631-109">value : 'T</span></span>

<span data-ttu-id="e8631-110">Wartość każdego elementu nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="e8631-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e8631-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="e8631-111">Output : 'T[]</span></span>

<span data-ttu-id="e8631-112">Nowa tablica o długości `length` , taka jak każdy element to `value` .</span><span class="sxs-lookup"><span data-stu-id="e8631-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e8631-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e8631-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8631-114">'C</span><span class="sxs-lookup"><span data-stu-id="e8631-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="e8631-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="e8631-115">Example</span></span>

<span data-ttu-id="e8631-116">Poniższy kod tworzy tablicę trzech wartości logicznych, z których każda jest równa `true` :</span><span class="sxs-lookup"><span data-stu-id="e8631-116">The following code creates an array of 3 Boolean values, each equal to `true`:</span></span>

```qsharp
let array = ConstantArray(3, true);
```