---
uid: Microsoft.Quantum.Canon.Repeat
title: Powtórz operację
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: cd572e5e082df94d762a0869ad2c1923fb71fd3d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205604"
---
# <a name="repeat-operation"></a><span data-ttu-id="53256-102">Powtórz operację</span><span class="sxs-lookup"><span data-stu-id="53256-102">Repeat operation</span></span>

<span data-ttu-id="53256-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53256-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53256-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="53256-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="53256-105">Powtarza operację określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="53256-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="53256-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="53256-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="53256-107">op: TInput = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="53256-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="53256-108">Operacja, która ma być wywoływana wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="53256-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="53256-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="53256-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="53256-110">Liczba wywołań `op` .</span><span class="sxs-lookup"><span data-stu-id="53256-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="53256-111">dane wejściowe: "TInput</span><span class="sxs-lookup"><span data-stu-id="53256-111">input : 'TInput</span></span>

<span data-ttu-id="53256-112">Dane wejściowe do przesłania `op` .</span><span class="sxs-lookup"><span data-stu-id="53256-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53256-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53256-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="53256-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="53256-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="53256-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="53256-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="53256-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="53256-116">See Also</span></span>

- [<span data-ttu-id="53256-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="53256-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="53256-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="53256-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="53256-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="53256-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="53256-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="53256-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)