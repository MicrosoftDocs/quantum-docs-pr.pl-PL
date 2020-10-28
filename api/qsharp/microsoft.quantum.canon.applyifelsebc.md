---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 032d92484dc96481cb981d9d8acfeed248a9116d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718212"
---
# <a name="applyifelsebc-operation"></a><span data-ttu-id="bc6d2-102">ApplyIfElseBC, operacja</span><span class="sxs-lookup"><span data-stu-id="bc6d2-102">ApplyIfElseBC operation</span></span>

<span data-ttu-id="bc6d2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bc6d2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bc6d2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc6d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc6d2-105">Stosuje jedną z dwóch operacji kontrolowanych, w zależności od wartości klasycznej.</span><span class="sxs-lookup"><span data-stu-id="bc6d2-105">Applies one of two controllable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="bc6d2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="bc6d2-106">Description</span></span>

<span data-ttu-id="bc6d2-107">Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="bc6d2-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="bc6d2-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bc6d2-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="bc6d2-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bc6d2-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bc6d2-110">Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="bc6d2-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-ctl"></a><span data-ttu-id="bc6d2-111">trueOp: t => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="bc6d2-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bc6d2-112">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana, gdy `bit` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="bc6d2-112">The controllable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="bc6d2-113">trueInput: 'T</span><span class="sxs-lookup"><span data-stu-id="bc6d2-113">trueInput : 'T</span></span>

<span data-ttu-id="bc6d2-114">Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="bc6d2-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-ctl"></a><span data-ttu-id="bc6d2-115">falseOp: ' U => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="bc6d2-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="bc6d2-116">Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana, gdy `bit` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="bc6d2-116">The controllable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="bc6d2-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="bc6d2-117">falseInput : 'U</span></span>

<span data-ttu-id="bc6d2-118">Dane wejściowe, które mają być dostarczone, `falseOp` gdy `bit` ma wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="bc6d2-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc6d2-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc6d2-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc6d2-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bc6d2-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc6d2-121">'C</span><span class="sxs-lookup"><span data-stu-id="bc6d2-121">'T</span></span>

<span data-ttu-id="bc6d2-122">Typ wejściowy operacji, `trueOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="bc6d2-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="bc6d2-123">' U</span><span class="sxs-lookup"><span data-stu-id="bc6d2-123">'U</span></span>

<span data-ttu-id="bc6d2-124">Typ wejściowy operacji, `falseOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="bc6d2-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc6d2-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bc6d2-125">See Also</span></span>

- [<span data-ttu-id="bc6d2-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="bc6d2-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="bc6d2-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="bc6d2-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="bc6d2-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="bc6d2-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="bc6d2-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="bc6d2-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="bc6d2-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="bc6d2-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)