---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716212"
---
# <a name="delayedc-function"></a><span data-ttu-id="be405-102">DelayedC, funkcja</span><span class="sxs-lookup"><span data-stu-id="be405-102">DelayedC function</span></span>

<span data-ttu-id="be405-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be405-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be405-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be405-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be405-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="be405-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="be405-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="be405-106">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="be405-107">op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be405-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="be405-108">Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej</span><span class="sxs-lookup"><span data-stu-id="be405-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="be405-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="be405-109">arg : 'T</span></span>

<span data-ttu-id="be405-110">Dane wejściowe, do których `op` zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="be405-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl"></a><span data-ttu-id="be405-111">Dane wyjściowe [Unit](xref:microsoft.quantum.lang-ref.unit) : => lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) jednostki</span><span class="sxs-lookup"><span data-stu-id="be405-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="be405-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="be405-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="be405-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="be405-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be405-114">'C</span><span class="sxs-lookup"><span data-stu-id="be405-114">'T</span></span>

<span data-ttu-id="be405-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="be405-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="be405-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="be405-116">See Also</span></span>

- [<span data-ttu-id="be405-117">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="be405-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="be405-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="be405-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)