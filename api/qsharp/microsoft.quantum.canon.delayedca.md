---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716221"
---
# <a name="delayedca-function"></a><span data-ttu-id="15568-102">DelayedCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="15568-102">DelayedCA function</span></span>

<span data-ttu-id="15568-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="15568-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="15568-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15568-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15568-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="15568-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="15568-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="15568-106">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="15568-107">op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik</span><span class="sxs-lookup"><span data-stu-id="15568-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="15568-108">Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej</span><span class="sxs-lookup"><span data-stu-id="15568-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="15568-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="15568-109">arg : 'T</span></span>

<span data-ttu-id="15568-110">Dane wejściowe, do których `op` zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="15568-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-ctl--adj"></a><span data-ttu-id="15568-111">Dane wyjściowe [Unit](xref:microsoft.quantum.lang-ref.unit) : => lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) jednostki i korekta</span><span class="sxs-lookup"><span data-stu-id="15568-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="15568-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="15568-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="15568-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="15568-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15568-114">'C</span><span class="sxs-lookup"><span data-stu-id="15568-114">'T</span></span>

<span data-ttu-id="15568-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="15568-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="15568-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="15568-116">See Also</span></span>

- [<span data-ttu-id="15568-117">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="15568-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="15568-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="15568-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)