---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: a8606cde976882bba0eb23467932b9ee0ed36696
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840618"
---
# <a name="delayca-operation"></a><span data-ttu-id="1613c-102">DelayCA, operacja</span><span class="sxs-lookup"><span data-stu-id="1613c-102">DelayCA operation</span></span>

<span data-ttu-id="1613c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1613c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1613c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1613c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1613c-105">Stosuje daną operację z opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="1613c-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="1613c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="1613c-106">Description</span></span>

<span data-ttu-id="1613c-107">Mając daną operację i dane wejściowe dla tej operacji, stosuje operację po udostępnieniu dodatkowych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="1613c-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="1613c-108">W szczególności wyrażenie `Delay(op, arg, _)` jest operacją, która stosuje się `op` do `arg` momentu wywołania.</span><span class="sxs-lookup"><span data-stu-id="1613c-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="1613c-109">Wyrażenie `Delay(op,arg,_)` umożliwia opóźnienie aplikacji `op` .</span><span class="sxs-lookup"><span data-stu-id="1613c-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="1613c-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="1613c-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="1613c-111">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="1613c-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="1613c-112">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="1613c-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="1613c-113">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="1613c-113">arg : 'T</span></span>

<span data-ttu-id="1613c-114">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="1613c-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="1613c-115">AUX: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1613c-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="1613c-116">Argument używany do opóźniania stosowania operacji przy użyciu częściowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="1613c-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1613c-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1613c-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1613c-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="1613c-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1613c-119">'C</span><span class="sxs-lookup"><span data-stu-id="1613c-119">'T</span></span>

<span data-ttu-id="1613c-120">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="1613c-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="1613c-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="1613c-121">See Also</span></span>

- [<span data-ttu-id="1613c-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="1613c-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="1613c-123">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="1613c-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)