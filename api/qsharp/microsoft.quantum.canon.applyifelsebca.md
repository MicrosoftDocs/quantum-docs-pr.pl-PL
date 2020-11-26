---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: d36b16298ea177f16b7bbb260f069bfe35b9a72f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218635"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="60d29-102">ApplyIfElseBCA, operacja</span><span class="sxs-lookup"><span data-stu-id="60d29-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="60d29-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60d29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60d29-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60d29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60d29-105">Stosuje jedną z dwóch operacji jednostkowych, w zależności od wartości klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="60d29-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="60d29-106">Opis</span><span class="sxs-lookup"><span data-stu-id="60d29-106">Description</span></span>

<span data-ttu-id="60d29-107">Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="60d29-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="60d29-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="60d29-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="60d29-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="60d29-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="60d29-110">Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="60d29-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj--ctl"></a><span data-ttu-id="60d29-111">trueOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="60d29-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="60d29-112">Operacja jednostkowa, która ma zostać zastosowana w przypadku programu `bit` `true` .</span><span class="sxs-lookup"><span data-stu-id="60d29-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="60d29-113">trueInput: 'T</span><span class="sxs-lookup"><span data-stu-id="60d29-113">trueInput : 'T</span></span>

<span data-ttu-id="60d29-114">Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="60d29-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj--ctl"></a><span data-ttu-id="60d29-115">falseOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="60d29-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="60d29-116">Operacja jednostkowa, która ma zostać zastosowana w przypadku programu `bit` `false` .</span><span class="sxs-lookup"><span data-stu-id="60d29-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="60d29-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="60d29-117">falseInput : 'U</span></span>

<span data-ttu-id="60d29-118">Dane wejściowe, które mają być dostarczone, `falseOp` gdy `bit` ma wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="60d29-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60d29-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60d29-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="60d29-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="60d29-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60d29-121">'C</span><span class="sxs-lookup"><span data-stu-id="60d29-121">'T</span></span>

<span data-ttu-id="60d29-122">Typ wejściowy operacji, `trueOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="60d29-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="60d29-123">' U</span><span class="sxs-lookup"><span data-stu-id="60d29-123">'U</span></span>

<span data-ttu-id="60d29-124">Typ wejściowy operacji, `falseOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="60d29-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="60d29-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="60d29-125">See Also</span></span>

- [<span data-ttu-id="60d29-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="60d29-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="60d29-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="60d29-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="60d29-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="60d29-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="60d29-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="60d29-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="60d29-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="60d29-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)