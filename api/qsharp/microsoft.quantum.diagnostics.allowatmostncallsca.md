---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 7caf33e33318bb74cb160436940eff9f0f2782cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202570"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="028a9-102">AllowAtMostNCallsCA, operacja</span><span class="sxs-lookup"><span data-stu-id="028a9-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="028a9-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="028a9-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="028a9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="028a9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="028a9-105">Między wywołaniem tej operacji i jej częścią, potwierdza, że dana operacja jest wywoływana co najwyżej określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="028a9-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="028a9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="028a9-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="028a9-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="028a9-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="028a9-108">Maksymalna liczba przypadków, gdy `op` może być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="028a9-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="028a9-109">op: "TInput =>" TOutput to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="028a9-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="028a9-110">Operacja, której wywołania mają być ograniczone.</span><span class="sxs-lookup"><span data-stu-id="028a9-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="028a9-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="028a9-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="028a9-112">Komunikat, który ma być wyświetlany w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="028a9-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="028a9-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="028a9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="028a9-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="028a9-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="028a9-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="028a9-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="028a9-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="028a9-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="028a9-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="028a9-117">Remarks</span></span>

<span data-ttu-id="028a9-118">Ta operacja może zostać zamieniona na elementy docelowe, które ich nie obsługują.</span><span class="sxs-lookup"><span data-stu-id="028a9-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>