---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: 45bd0f46fb2e28c5c9aaa21cb7ec065baf279d2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718116"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="5e6b8-102">ApplyIfElseRC, operacja</span><span class="sxs-lookup"><span data-stu-id="5e6b8-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="5e6b8-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5e6b8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5e6b8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e6b8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e6b8-105">Stosuje jedną z dwóch operacji kontrolowanych, w zależności od wartości klasycznego wyniku.</span><span class="sxs-lookup"><span data-stu-id="5e6b8-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="5e6b8-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5e6b8-106">Description</span></span>

<span data-ttu-id="5e6b8-107">W związku z `result` tym, stosuje operację `zeroOp` za pomocą `zeroInput` jako dane wejściowe `result` , gdy jest równe `Zero` , i ma zastosowanie, `oneOp(oneInput)` gdy `result == One` .</span><span class="sxs-lookup"><span data-stu-id="5e6b8-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="5e6b8-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5e6b8-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="5e6b8-109">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="5e6b8-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="5e6b8-110">Wynik pomiaru służący do określenia `zeroOp` , czy lub `oneOp` ma zostać zastosowany.</span><span class="sxs-lookup"><span data-stu-id="5e6b8-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit-ctl"></a><span data-ttu-id="5e6b8-111">zeroOp: t => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="5e6b8-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5e6b8-112">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana w przypadku `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="5e6b8-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="5e6b8-113">zeroInput: 'T</span><span class="sxs-lookup"><span data-stu-id="5e6b8-113">zeroInput : 'T</span></span>

<span data-ttu-id="5e6b8-114">Dane wejściowe, które mają być dostarczone przez `zeroOp` `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="5e6b8-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit-ctl"></a><span data-ttu-id="5e6b8-115">oneOp: ' U => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="5e6b8-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5e6b8-116">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana w przypadku `result == One` .</span><span class="sxs-lookup"><span data-stu-id="5e6b8-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="5e6b8-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="5e6b8-117">oneInput : 'U</span></span>

<span data-ttu-id="5e6b8-118">Dane wejściowe, które mają być dostarczone przez `oneOp` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="5e6b8-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e6b8-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e6b8-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5e6b8-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5e6b8-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e6b8-121">'C</span><span class="sxs-lookup"><span data-stu-id="5e6b8-121">'T</span></span>

<span data-ttu-id="5e6b8-122">Typ wejściowy operacji, `zeroOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="5e6b8-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="5e6b8-123">' U</span><span class="sxs-lookup"><span data-stu-id="5e6b8-123">'U</span></span>

<span data-ttu-id="5e6b8-124">Typ wejściowy operacji, `oneOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="5e6b8-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e6b8-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5e6b8-125">See Also</span></span>

- [<span data-ttu-id="5e6b8-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="5e6b8-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="5e6b8-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="5e6b8-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="5e6b8-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="5e6b8-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="5e6b8-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="5e6b8-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="5e6b8-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="5e6b8-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)