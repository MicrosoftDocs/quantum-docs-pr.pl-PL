---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5dc4377c696e14b505c63701c2f5ca0dadca672
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718896"
---
# <a name="sequencei-function"></a><span data-ttu-id="07f10-102">SequenceI, funkcja</span><span class="sxs-lookup"><span data-stu-id="07f10-102">SequenceI function</span></span>

<span data-ttu-id="07f10-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="07f10-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="07f10-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07f10-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07f10-105">Pobierz tablicę liczb całkowitych w danym interwale.</span><span class="sxs-lookup"><span data-stu-id="07f10-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="07f10-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="07f10-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="07f10-107">od: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07f10-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07f10-108">Zamknięty indeks początkowy interwału.</span><span class="sxs-lookup"><span data-stu-id="07f10-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="07f10-109">do: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07f10-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07f10-110">Łączny indeks końcowy interwału, który nie jest mniejszy niż `from` .</span><span class="sxs-lookup"><span data-stu-id="07f10-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="07f10-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="07f10-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="07f10-112">Tablica zawierająca sekwencję liczb `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="07f10-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>