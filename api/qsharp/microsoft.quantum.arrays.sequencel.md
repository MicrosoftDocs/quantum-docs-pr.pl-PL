---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Funkcja Sequence
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718881"
---
# <a name="sequencel-function"></a><span data-ttu-id="54774-102">Funkcja Sequence</span><span class="sxs-lookup"><span data-stu-id="54774-102">SequenceL function</span></span>

<span data-ttu-id="54774-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="54774-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="54774-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54774-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54774-105">Pobierz tablicę liczb całkowitych w danym interwale.</span><span class="sxs-lookup"><span data-stu-id="54774-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="54774-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="54774-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="54774-107">z: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="54774-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="54774-108">Zamknięty indeks początkowy interwału.</span><span class="sxs-lookup"><span data-stu-id="54774-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="54774-109">do: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="54774-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="54774-110">Łączny indeks końcowy interwału, który nie jest mniejszy niż `from` .</span><span class="sxs-lookup"><span data-stu-id="54774-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="54774-111">Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="54774-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="54774-112">Tablica zawierająca sekwencję liczb `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="54774-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="54774-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="54774-113">Remarks</span></span>

<span data-ttu-id="54774-114">Różnica między `from` i `to` musi pasować do `Int` wartości.</span><span class="sxs-lookup"><span data-stu-id="54774-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>