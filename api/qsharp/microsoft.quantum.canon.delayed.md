---
uid: Microsoft.Quantum.Canon.Delayed
title: Funkcja opóźniona
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716254"
---
# <a name="delayed-function"></a><span data-ttu-id="d5571-102">Funkcja opóźniona</span><span class="sxs-lookup"><span data-stu-id="d5571-102">Delayed function</span></span>

<span data-ttu-id="d5571-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5571-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5571-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5571-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5571-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="d5571-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a><span data-ttu-id="d5571-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d5571-106">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="d5571-107">op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="d5571-107">op : 'T => 'U</span></span> 

<span data-ttu-id="d5571-108">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="d5571-108">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="d5571-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="d5571-109">arg : 'T</span></span>

<span data-ttu-id="d5571-110">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="d5571-110">The input to which the operation is applied.</span></span>



## <a name="output--unit--u"></a><span data-ttu-id="d5571-111">Dane wyjściowe: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U</span><span class="sxs-lookup"><span data-stu-id="d5571-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => 'U</span></span> 

<span data-ttu-id="d5571-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="d5571-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d5571-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d5571-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5571-114">'C</span><span class="sxs-lookup"><span data-stu-id="d5571-114">'T</span></span>

<span data-ttu-id="d5571-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="d5571-115">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="d5571-116">' U</span><span class="sxs-lookup"><span data-stu-id="d5571-116">'U</span></span>

<span data-ttu-id="d5571-117">Zwracany typ operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="d5571-117">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5571-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d5571-118">See Also</span></span>

- [<span data-ttu-id="d5571-119">Microsoft. Quantum. Canon. DelayedC</span><span class="sxs-lookup"><span data-stu-id="d5571-119">Microsoft.Quantum.Canon.DelayedC</span></span>](xref:Microsoft.Quantum.Canon.DelayedC)
- [<span data-ttu-id="d5571-120">Microsoft. Quantum. Canon. opóźnione</span><span class="sxs-lookup"><span data-stu-id="d5571-120">Microsoft.Quantum.Canon.DelayedA</span></span>](xref:Microsoft.Quantum.Canon.DelayedA)
- [<span data-ttu-id="d5571-121">Microsoft. Quantum. Canon. DelayedCA</span><span class="sxs-lookup"><span data-stu-id="d5571-121">Microsoft.Quantum.Canon.DelayedCA</span></span>](xref:Microsoft.Quantum.Canon.DelayedCA)
- [<span data-ttu-id="d5571-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="d5571-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)