---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: 1a9975d2d2026749238430b247cf47738de545cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713062"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="15e1e-102">AllowAtMostNCallsCA, operacja</span><span class="sxs-lookup"><span data-stu-id="15e1e-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="15e1e-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="15e1e-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="15e1e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15e1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15e1e-105">Między wywołaniem tej operacji i jej częścią, potwierdza, że dana operacja jest wywoływana co najwyżej określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="15e1e-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="15e1e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="15e1e-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="15e1e-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="15e1e-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="15e1e-108">Maksymalna liczba przypadków, gdy `op` może być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="15e1e-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput-adj--ctl"></a><span data-ttu-id="15e1e-109">op: ' TInput => ' TOutput przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="15e1e-109">op : 'TInput => 'TOutput Adj + Ctl</span></span>

<span data-ttu-id="15e1e-110">Operacja, której wywołania mają być ograniczone.</span><span class="sxs-lookup"><span data-stu-id="15e1e-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="15e1e-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="15e1e-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="15e1e-112">Komunikat, który ma być wyświetlany w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="15e1e-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="15e1e-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15e1e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="15e1e-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="15e1e-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="15e1e-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="15e1e-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="15e1e-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="15e1e-116">'TOutput</span></span>



## <a name="remarks"></a><span data-ttu-id="15e1e-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="15e1e-117">Remarks</span></span>

<span data-ttu-id="15e1e-118">Ta operacja może zostać zamieniona na elementy docelowe, które ich nie obsługują.</span><span class="sxs-lookup"><span data-stu-id="15e1e-118">This operation may be replaced by a no-op on targets which do not support it.</span></span>