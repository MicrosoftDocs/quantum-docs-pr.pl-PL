---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209999"
---
# <a name="drawmany-operation"></a><span data-ttu-id="663c9-102">DrawMany, operacja</span><span class="sxs-lookup"><span data-stu-id="663c9-102">DrawMany operation</span></span>

<span data-ttu-id="663c9-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="663c9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="663c9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="663c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="663c9-105">Powtarza operację dla danej liczby próbek, zbierając wyniki wyjściowe w tablicy.</span><span class="sxs-lookup"><span data-stu-id="663c9-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="663c9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="663c9-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="663c9-107">op: "TInput =>" TOutput</span><span class="sxs-lookup"><span data-stu-id="663c9-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="663c9-108">Operacja, która ma być wywoływana wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="663c9-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="663c9-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="663c9-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="663c9-110">Liczba próbek wywołujących `op` do zebrania.</span><span class="sxs-lookup"><span data-stu-id="663c9-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="663c9-111">dane wejściowe: "TInput</span><span class="sxs-lookup"><span data-stu-id="663c9-111">input : 'TInput</span></span>

<span data-ttu-id="663c9-112">Dane wejściowe do przesłania `op` .</span><span class="sxs-lookup"><span data-stu-id="663c9-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="663c9-113">Dane wyjściowe: "TOutput []</span><span class="sxs-lookup"><span data-stu-id="663c9-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="663c9-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="663c9-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="663c9-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="663c9-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="663c9-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="663c9-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="663c9-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="663c9-117">See Also</span></span>

- [<span data-ttu-id="663c9-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="663c9-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)