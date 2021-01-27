---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833309"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="bd140-102">IntAsBoolArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="bd140-102">IntAsBoolArray function</span></span>

<span data-ttu-id="bd140-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="bd140-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="bd140-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bd140-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bd140-105">Tworzy binarną reprezentację nieujemnej liczby całkowitej przy użyciu reprezentacji little-endian dla zwróconej tablicy.</span><span class="sxs-lookup"><span data-stu-id="bd140-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="bd140-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bd140-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="bd140-107">Liczba: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bd140-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bd140-108">Nieujemna liczba całkowita do przekonwertowania na tablicę wartości logicznych.</span><span class="sxs-lookup"><span data-stu-id="bd140-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="bd140-109">bity: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bd140-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bd140-110">Liczba bitów w reprezentacji binarnej `number` .</span><span class="sxs-lookup"><span data-stu-id="bd140-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="bd140-111">Output: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="bd140-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="bd140-112">Tablica wartości logicznych reprezentujących `number` .</span><span class="sxs-lookup"><span data-stu-id="bd140-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd140-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bd140-113">Remarks</span></span>

<span data-ttu-id="bd140-114">Wartość wejściowa `bits` musi należeć do zakresu od 0 do 63.</span><span class="sxs-lookup"><span data-stu-id="bd140-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="bd140-115">Wartość wejściowa `number` musi należeć do zakresu od 0 do $2 ^ {\texttt{BITS}}-$1.</span><span class="sxs-lookup"><span data-stu-id="bd140-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>