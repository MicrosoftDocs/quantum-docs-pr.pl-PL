---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224347"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="1db76-102">IntAsBoolArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="1db76-102">IntAsBoolArray function</span></span>

<span data-ttu-id="1db76-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="1db76-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="1db76-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1db76-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1db76-105">Tworzy binarną reprezentację dodatniej liczby całkowitej przy użyciu reprezentacji little-endian dla zwróconej tablicy.</span><span class="sxs-lookup"><span data-stu-id="1db76-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="1db76-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1db76-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="1db76-107">Liczba: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1db76-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1db76-108">Dodatnia liczba całkowita, która ma zostać przekonwertowana na tablicę wartości logicznych.</span><span class="sxs-lookup"><span data-stu-id="1db76-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="1db76-109">bity: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1db76-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1db76-110">Liczba bitów w reprezentacji binarnej `number` .</span><span class="sxs-lookup"><span data-stu-id="1db76-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1db76-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1db76-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1db76-112">Tablica wartości logicznych reprezentujących `number` .</span><span class="sxs-lookup"><span data-stu-id="1db76-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1db76-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="1db76-113">Remarks</span></span>

<span data-ttu-id="1db76-114">Wartość wejściowa `bits` musi należeć do zakresu od 0 do 63.</span><span class="sxs-lookup"><span data-stu-id="1db76-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="1db76-115">Wartość wejściowa `number` musi należeć do zakresu od 0 do $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="1db76-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>