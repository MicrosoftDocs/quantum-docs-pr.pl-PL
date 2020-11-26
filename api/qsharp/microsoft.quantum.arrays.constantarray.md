---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210067"
---
# <a name="constantarray-function"></a><span data-ttu-id="9f1d6-102">ConstantArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="9f1d6-102">ConstantArray function</span></span>

<span data-ttu-id="9f1d6-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9f1d6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9f1d6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f1d6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f1d6-105">Tworzy tablicę o podaną długość ze wszystkimi elementami równymi podaną wartością.</span><span class="sxs-lookup"><span data-stu-id="9f1d6-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="9f1d6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9f1d6-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="9f1d6-107">Długość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9f1d6-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9f1d6-108">Długość nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="9f1d6-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="9f1d6-109">wartość: 'T</span><span class="sxs-lookup"><span data-stu-id="9f1d6-109">value : 'T</span></span>

<span data-ttu-id="9f1d6-110">Wartość każdego elementu nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="9f1d6-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="9f1d6-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="9f1d6-111">Output : 'T[]</span></span>

<span data-ttu-id="9f1d6-112">Nowa tablica o długości `length` , taka jak każdy element to `value` .</span><span class="sxs-lookup"><span data-stu-id="9f1d6-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9f1d6-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9f1d6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9f1d6-114">'C</span><span class="sxs-lookup"><span data-stu-id="9f1d6-114">'T</span></span>

