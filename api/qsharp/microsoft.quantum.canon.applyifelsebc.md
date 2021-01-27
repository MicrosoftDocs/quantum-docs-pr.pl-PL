---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841816"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="f7c5d-102">ApplyIfElseBC, operacja</span><span class="sxs-lookup"><span data-stu-id="f7c5d-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="f7c5d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7c5d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7c5d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7c5d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7c5d-105">Stosuje jedną z dwóch operacji kontrolowanych, w zależności od wartości klasycznej.</span><span class="sxs-lookup"><span data-stu-id="f7c5d-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="f7c5d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f7c5d-106">Description</span></span>

<span data-ttu-id="f7c5d-107">Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="f7c5d-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="f7c5d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f7c5d-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="f7c5d-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f7c5d-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f7c5d-110">Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="f7c5d-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-ctl"></a><span data-ttu-id="f7c5d-111">trueOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="f7c5d-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f7c5d-112">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana, gdy `bit` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="f7c5d-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="f7c5d-113">trueInput: 'T</span><span class="sxs-lookup"><span data-stu-id="f7c5d-113">trueInput : 'T</span></span>

<span data-ttu-id="f7c5d-114">Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="f7c5d-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-ctl"></a><span data-ttu-id="f7c5d-115">falseOp: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="f7c5d-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f7c5d-116">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana, gdy `bit` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="f7c5d-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="f7c5d-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="f7c5d-117">falseInput : 'U</span></span>

<span data-ttu-id="f7c5d-118">Dane wejściowe, które mają być dostarczone, `falseOp` gdy `bit` ma wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="f7c5d-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7c5d-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7c5d-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f7c5d-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f7c5d-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7c5d-121">'C</span><span class="sxs-lookup"><span data-stu-id="f7c5d-121">'T</span></span>

<span data-ttu-id="f7c5d-122">Typ wejściowy operacji, `trueOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="f7c5d-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="f7c5d-123">' U</span><span class="sxs-lookup"><span data-stu-id="f7c5d-123">'U</span></span>

<span data-ttu-id="f7c5d-124">Typ wejściowy operacji, `falseOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="f7c5d-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7c5d-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f7c5d-125">See Also</span></span>

- [<span data-ttu-id="f7c5d-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="f7c5d-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="f7c5d-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="f7c5d-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="f7c5d-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="f7c5d-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="f7c5d-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="f7c5d-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="f7c5d-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="f7c5d-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)