---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719412"
---
# <a name="constantarray-function"></a><span data-ttu-id="578b7-102">ConstantArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="578b7-102">ConstantArray function</span></span>

<span data-ttu-id="578b7-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="578b7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="578b7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="578b7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="578b7-105">Tworzy tablicę o podaną długość ze wszystkimi elementami równymi podaną wartością.</span><span class="sxs-lookup"><span data-stu-id="578b7-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="578b7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="578b7-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="578b7-107">Długość: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="578b7-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="578b7-108">Długość nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="578b7-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="578b7-109">wartość: 'T</span><span class="sxs-lookup"><span data-stu-id="578b7-109">value : 'T</span></span>

<span data-ttu-id="578b7-110">Wartość każdego elementu nowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="578b7-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="578b7-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="578b7-111">Output : 'T[]</span></span>

<span data-ttu-id="578b7-112">Nowa tablica o długości `length` , taka jak każdy element to `value` .</span><span class="sxs-lookup"><span data-stu-id="578b7-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="578b7-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="578b7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="578b7-114">'C</span><span class="sxs-lookup"><span data-stu-id="578b7-114">'T</span></span>

