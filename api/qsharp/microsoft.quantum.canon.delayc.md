---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216493"
---
# <a name="delayc-operation"></a><span data-ttu-id="67def-102">DelayC, operacja</span><span class="sxs-lookup"><span data-stu-id="67def-102">DelayC operation</span></span>

<span data-ttu-id="67def-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="67def-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="67def-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67def-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67def-105">Stosuje daną operację z opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="67def-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="67def-106">Opis</span><span class="sxs-lookup"><span data-stu-id="67def-106">Description</span></span>

<span data-ttu-id="67def-107">Mając daną operację i dane wejściowe dla tej operacji, stosuje operację po udostępnieniu dodatkowych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="67def-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="67def-108">W szczególności wyrażenie `Delay(op, arg, _)` jest operacją, która stosuje się `op` do `arg` momentu wywołania.</span><span class="sxs-lookup"><span data-stu-id="67def-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="67def-109">Wyrażenie `Delay(op,arg,_)` umożliwia opóźnienie aplikacji `op` .</span><span class="sxs-lookup"><span data-stu-id="67def-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="67def-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="67def-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="67def-111">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="67def-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="67def-112">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="67def-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="67def-113">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="67def-113">arg : 'T</span></span>

<span data-ttu-id="67def-114">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="67def-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="67def-115">AUX: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67def-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="67def-116">Argument używany do opóźniania stosowania operacji przy użyciu częściowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="67def-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="67def-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="67def-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="67def-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="67def-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="67def-119">'C</span><span class="sxs-lookup"><span data-stu-id="67def-119">'T</span></span>

<span data-ttu-id="67def-120">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="67def-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="67def-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="67def-121">See Also</span></span>

- [<span data-ttu-id="67def-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="67def-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="67def-123">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="67def-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)