---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: ce08907646c3210f76244f29aa0d936e2bd6ee43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718200"
---
# <a name="applyifelseba-operation"></a><span data-ttu-id="17fe3-102">ApplyIfElseBA, operacja</span><span class="sxs-lookup"><span data-stu-id="17fe3-102">ApplyIfElseBA operation</span></span>

<span data-ttu-id="17fe3-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="17fe3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="17fe3-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="17fe3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="17fe3-105">Stosuje jedną z dwóch operacji przylegających, w zależności od wartości klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="17fe3-105">Applies one of two adjointable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="17fe3-106">Opis</span><span class="sxs-lookup"><span data-stu-id="17fe3-106">Description</span></span>

<span data-ttu-id="17fe3-107">Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="17fe3-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="17fe3-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="17fe3-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="17fe3-109">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="17fe3-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="17fe3-110">Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="17fe3-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj"></a><span data-ttu-id="17fe3-111">trueOp: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17fe3-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="17fe3-112">Operacja przylegania, która ma zostać zastosowana, gdy `bit` ma wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="17fe3-112">The adjointable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="17fe3-113">trueInput: 'T</span><span class="sxs-lookup"><span data-stu-id="17fe3-113">trueInput : 'T</span></span>

<span data-ttu-id="17fe3-114">Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .</span><span class="sxs-lookup"><span data-stu-id="17fe3-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj"></a><span data-ttu-id="17fe3-115">falseOp: ' U => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17fe3-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="17fe3-116">Operacja przylegania, która ma zostać zastosowana, gdy `bit` ma wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="17fe3-116">The adjointable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="17fe3-117">falseInput: ' U</span><span class="sxs-lookup"><span data-stu-id="17fe3-117">falseInput : 'U</span></span>

<span data-ttu-id="17fe3-118">Dane wejściowe, które mają być dostarczone, `falseOp` gdy `bit` ma wartość `false` .</span><span class="sxs-lookup"><span data-stu-id="17fe3-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="17fe3-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="17fe3-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="17fe3-120">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="17fe3-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="17fe3-121">'C</span><span class="sxs-lookup"><span data-stu-id="17fe3-121">'T</span></span>

<span data-ttu-id="17fe3-122">Typ wejściowy operacji, `trueOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="17fe3-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="17fe3-123">' U</span><span class="sxs-lookup"><span data-stu-id="17fe3-123">'U</span></span>

<span data-ttu-id="17fe3-124">Typ wejściowy operacji, `falseOp` która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="17fe3-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="17fe3-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="17fe3-125">See Also</span></span>

- [<span data-ttu-id="17fe3-126">Microsoft. Quantum. Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="17fe3-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="17fe3-127">Microsoft. Quantum. Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="17fe3-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="17fe3-128">Microsoft. Quantum. Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="17fe3-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="17fe3-129">Microsoft. Quantum. Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="17fe3-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="17fe3-130">Microsoft. Quantum. Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="17fe3-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)