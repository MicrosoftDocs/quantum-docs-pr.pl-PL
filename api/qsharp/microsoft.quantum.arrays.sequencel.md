---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funkcja Sequence
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220267"
---
# <a name="sequencel-function"></a><span data-ttu-id="b71c5-102">Funkcja Sequence</span><span class="sxs-lookup"><span data-stu-id="b71c5-102">SequenceL function</span></span>

<span data-ttu-id="b71c5-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b71c5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b71c5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b71c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b71c5-105">Pobierz tablicę liczb całkowitych w danym interwale.</span><span class="sxs-lookup"><span data-stu-id="b71c5-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="b71c5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b71c5-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="b71c5-107">z: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b71c5-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b71c5-108">Zamknięty indeks początkowy interwału.</span><span class="sxs-lookup"><span data-stu-id="b71c5-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="b71c5-109">do: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b71c5-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b71c5-110">Łączny indeks końcowy interwału, który nie jest mniejszy niż `from` .</span><span class="sxs-lookup"><span data-stu-id="b71c5-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="b71c5-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="b71c5-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="b71c5-112">Tablica zawierająca sekwencję liczb `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="b71c5-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b71c5-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b71c5-113">Remarks</span></span>

<span data-ttu-id="b71c5-114">Różnica między `from` i `to` musi pasować do `Int` wartości.</span><span class="sxs-lookup"><span data-stu-id="b71c5-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>