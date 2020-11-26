---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 24606486b3d5703065a7c7f62d3bbc7e3d07615f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205409"
---
# <a name="repeatca-operation"></a><span data-ttu-id="e9cf8-102">RepeatCA, operacja</span><span class="sxs-lookup"><span data-stu-id="e9cf8-102">RepeatCA operation</span></span>

<span data-ttu-id="e9cf8-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e9cf8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e9cf8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9cf8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9cf8-105">Powtarza operację określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="e9cf8-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9cf8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e9cf8-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="e9cf8-107">op: element "TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="e9cf8-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e9cf8-108">Operacja, która ma być wywoływana wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="e9cf8-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="e9cf8-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9cf8-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9cf8-110">Liczba wywołań `op` .</span><span class="sxs-lookup"><span data-stu-id="e9cf8-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="e9cf8-111">dane wejściowe: "TInput</span><span class="sxs-lookup"><span data-stu-id="e9cf8-111">input : 'TInput</span></span>

<span data-ttu-id="e9cf8-112">Dane wejściowe do przesłania `op` .</span><span class="sxs-lookup"><span data-stu-id="e9cf8-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9cf8-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9cf8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e9cf8-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e9cf8-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="e9cf8-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="e9cf8-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="e9cf8-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e9cf8-116">See Also</span></span>

- [<span data-ttu-id="e9cf8-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="e9cf8-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="e9cf8-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="e9cf8-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="e9cf8-119">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="e9cf8-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="e9cf8-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="e9cf8-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)