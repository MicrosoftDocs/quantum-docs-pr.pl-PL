---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNCallsCA
title: AllowAtMostNCallsCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNCallsCA
qsharp.summary: Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.
ms.openlocfilehash: bb6ba2615b571b0d9d056b93f8e36d2dec0c4a21
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853535"
---
# <a name="allowatmostncallsca-operation"></a><span data-ttu-id="bdfa6-102">AllowAtMostNCallsCA, operacja</span><span class="sxs-lookup"><span data-stu-id="bdfa6-102">AllowAtMostNCallsCA operation</span></span>

<span data-ttu-id="bdfa6-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bdfa6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bdfa6-105">Między wywołaniem tej operacji i jej częścią, potwierdza, że dana operacja jest wywoływana co najwyżej określoną liczbę razy.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-105">Between a call to this operation and its adjoint, asserts that a given operation is called at most a certain number of times.</span></span>

```qsharp
operation AllowAtMostNCallsCA<'TInput, 'TOutput> (nTimes : Int, op : ('TInput => 'TOutput is Adj + Ctl), message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="bdfa6-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bdfa6-106">Input</span></span>

### <a name="ntimes--int"></a><span data-ttu-id="bdfa6-107">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-107">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bdfa6-108">Maksymalna liczba przypadków, gdy `op` może być wywoływana.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-108">The maximum number of times that `op` may be called.</span></span>


### <a name="op--tinput--toutput--is-adj--ctl"></a><span data-ttu-id="bdfa6-109">op: "TInput =>" TOutput to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="bdfa6-109">op : 'TInput => 'TOutput  is Adj + Ctl</span></span>

<span data-ttu-id="bdfa6-110">Operacja, której wywołania mają być ograniczone.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-110">An operation whose calls are to be restricted.</span></span>


### <a name="message--string"></a><span data-ttu-id="bdfa6-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bdfa6-112">Komunikat, który ma być wyświetlany w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-112">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bdfa6-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bdfa6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bdfa6-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bdfa6-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="bdfa6-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="bdfa6-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="bdfa6-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="bdfa6-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="bdfa6-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="bdfa6-117">Example</span></span>

<span data-ttu-id="bdfa6-118">Poniższy fragment kodu zakończy się niepowodzeniem podczas wykonywania na maszynach, które obsługują tę diagnostykę:</span><span class="sxs-lookup"><span data-stu-id="bdfa6-118">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
using (register = Qubit[4]) {
    within {
        AllowAtMostNCallsCA(3, H, "Too many calls to H.");
    } apply {
        // Fails since this calls H four times, rather than the
        // allowed maximum of three.
        ApplyToEach(H, register);
    }
}
```

## <a name="remarks"></a><span data-ttu-id="bdfa6-119">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bdfa6-119">Remarks</span></span>

<span data-ttu-id="bdfa6-120">Ta operacja może zostać zamieniona na elementy docelowe, które ich nie obsługują.</span><span class="sxs-lookup"><span data-stu-id="bdfa6-120">This operation may be replaced by a no-op on targets which do not support it.</span></span>