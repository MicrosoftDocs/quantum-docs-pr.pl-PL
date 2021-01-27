---
uid: Microsoft.Quantum.Canon.Delayed
title: Funkcja opóźniona
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 40fcc7d0a178fdb18437b4d6c96542db593347b4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840582"
---
# <a name="delayed-function"></a><span data-ttu-id="4b325-102">Funkcja opóźniona</span><span class="sxs-lookup"><span data-stu-id="4b325-102">Delayed function</span></span>

<span data-ttu-id="4b325-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b325-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b325-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b325-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b325-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="4b325-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="4b325-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4b325-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="4b325-107">op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="4b325-107">op : 'T => 'U</span></span> 

<span data-ttu-id="4b325-108">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4b325-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="4b325-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="4b325-109">arg : 'T</span></span>

<span data-ttu-id="4b325-110">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="4b325-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="4b325-111">Dane wyjściowe: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="4b325-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="4b325-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="4b325-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4b325-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4b325-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b325-114">'C</span><span class="sxs-lookup"><span data-stu-id="4b325-114">'T</span></span>

<span data-ttu-id="4b325-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="4b325-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="4b325-116">' U</span><span class="sxs-lookup"><span data-stu-id="4b325-116">'U</span></span>

<span data-ttu-id="4b325-117">Zwracany typ operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="4b325-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b325-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4b325-118">See Also</span></span>

- [<span data-ttu-id="4b325-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="4b325-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="4b325-120">Microsoft. Quantum. Canon. opóźnione</span><span class="sxs-lookup"><span data-stu-id="4b325-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="4b325-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="4b325-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="4b325-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="4b325-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)