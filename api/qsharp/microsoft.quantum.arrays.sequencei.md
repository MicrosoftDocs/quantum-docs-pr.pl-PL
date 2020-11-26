---
uid: Microsoft.Quantum.Arrays.SequenceI
title: SequenceI, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceI
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 5f03e5f2baff8077c1fa3fb5f1f079528ef0e215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220301"
---
# <a name="sequencei-function"></a><span data-ttu-id="ffe1b-102">SequenceI, funkcja</span><span class="sxs-lookup"><span data-stu-id="ffe1b-102">SequenceI function</span></span>

<span data-ttu-id="ffe1b-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ffe1b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ffe1b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ffe1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ffe1b-105">Pobierz tablicę liczb całkowitych w danym interwale.</span><span class="sxs-lookup"><span data-stu-id="ffe1b-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceI (from : Int, to : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="ffe1b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ffe1b-106">Input</span></span>

### <a name="from--int"></a><span data-ttu-id="ffe1b-107">od: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffe1b-107">from : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffe1b-108">Zamknięty indeks początkowy interwału.</span><span class="sxs-lookup"><span data-stu-id="ffe1b-108">An inclusive start index of the interval.</span></span>


### <a name="to--int"></a><span data-ttu-id="ffe1b-109">do: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ffe1b-109">to : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ffe1b-110">Łączny indeks końcowy interwału, który nie jest mniejszy niż `from` .</span><span class="sxs-lookup"><span data-stu-id="ffe1b-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ffe1b-111">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="ffe1b-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="ffe1b-112">Tablica zawierająca sekwencję liczb `from` , `from + 1` ,..., `to` .</span><span class="sxs-lookup"><span data-stu-id="ffe1b-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>