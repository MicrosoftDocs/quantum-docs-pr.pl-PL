---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209489"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="68a08-102">ApplyIfElseRC, operacja</span><span class="sxs-lookup"><span data-stu-id="68a08-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="68a08-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="68a08-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="68a08-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68a08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="68a08-105">Stosuje jedną z dwóch operacji kontrolowanych, w zależności od wartości klasycznego wyniku.</span><span class="sxs-lookup"><span data-stu-id="68a08-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="68a08-106">Opis</span><span class="sxs-lookup"><span data-stu-id="68a08-106">Description</span></span>

<span data-ttu-id="68a08-107">W związku z `result` tym, stosuje operację `zeroOp` za pomocą `zeroInput` jako dane wejściowe `result` , gdy jest równe `Zero` , i ma zastosowanie, `oneOp(oneInput)` gdy `result == One` .</span><span class="sxs-lookup"><span data-stu-id="68a08-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="68a08-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="68a08-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="68a08-109">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="68a08-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="68a08-110">Wynik pomiaru służący do określenia `zeroOp` , czy lub `oneOp` ma zostać zastosowany.</span><span class="sxs-lookup"><span data-stu-id="68a08-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-ctl"></a><span data-ttu-id="68a08-111">zeroOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="68a08-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="68a08-112">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana w przypadku `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="68a08-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="68a08-113">zeroInput: 'T</span><span class="sxs-lookup"><span data-stu-id="68a08-113">zeroInput : 'T</span></span>

<span data-ttu-id="68a08-114">Dane wejściowe, które mają być dostarczone przez `zeroOp` `result == Zero` .</span><span class="sxs-lookup"><span data-stu-id="68a08-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-ctl"></a><span data-ttu-id="68a08-115">oneOp: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="68a08-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="68a08-116">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana w przypadku `result == One` .</span><span class="sxs-lookup"><span data-stu-id="68a08-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="68a08-117">oneInput: ' U</span><span class="sxs-lookup"><span data-stu-id="68a08-117">oneInput : 'U</span></span>

<span data-ttu-id="68a08-118">Dane wejściowe, które mają być dostarczone przez `oneOp` `result == One` .</span><span class="sxs-lookup"><span data-stu-id="68a08-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="68a08-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="68a08-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="68a08-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="68a08-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="68a08-121">'C</span><span class="sxs-lookup"><span data-stu-id="68a08-121">'T</span></span>

<span data-ttu-id="68a08-122">Typ wejściowy operacji, `zeroOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="68a08-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="68a08-123">' U</span><span class="sxs-lookup"><span data-stu-id="68a08-123">'U</span></span>

<span data-ttu-id="68a08-124">Typ wejściowy operacji, `oneOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="68a08-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="68a08-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="68a08-125">See Also</span></span>

- [<span data-ttu-id="68a08-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="68a08-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="68a08-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="68a08-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="68a08-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="68a08-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="68a08-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="68a08-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="68a08-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="68a08-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)