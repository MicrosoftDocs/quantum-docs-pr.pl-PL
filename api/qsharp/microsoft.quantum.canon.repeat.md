---
uid: Microsoft.Quantum.Canon.Repeat
title: Powtórz operację
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 5aedd056b851b8d8d7c25a32eb22587292e132a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715596"
---
# <a name="repeat-operation"></a><span data-ttu-id="bac3f-102">Powtórz operację</span><span class="sxs-lookup"><span data-stu-id="bac3f-102">Repeat operation</span></span>

<span data-ttu-id="bac3f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bac3f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bac3f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bac3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bac3f-105">Powtarza operację określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="bac3f-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="bac3f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bac3f-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="bac3f-107">op: TInput = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="bac3f-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="bac3f-108">Operacja, która ma być wywoływana wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="bac3f-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="bac3f-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bac3f-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bac3f-110">Liczba wywołań `op` .</span><span class="sxs-lookup"><span data-stu-id="bac3f-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="bac3f-111">dane wejściowe: "TInput</span><span class="sxs-lookup"><span data-stu-id="bac3f-111">input : 'TInput</span></span>

<span data-ttu-id="bac3f-112">Dane wejściowe do przesłania `op` .</span><span class="sxs-lookup"><span data-stu-id="bac3f-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bac3f-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bac3f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bac3f-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bac3f-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="bac3f-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="bac3f-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="bac3f-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bac3f-116">See Also</span></span>

- [<span data-ttu-id="bac3f-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="bac3f-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="bac3f-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="bac3f-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="bac3f-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="bac3f-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="bac3f-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="bac3f-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)