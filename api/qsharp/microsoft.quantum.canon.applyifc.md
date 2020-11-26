---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218720"
---
# <a name="applyifc-operation"></a><span data-ttu-id="6efed-102">ApplyIfC, operacja</span><span class="sxs-lookup"><span data-stu-id="6efed-102">ApplyIfC operation</span></span>

<span data-ttu-id="6efed-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6efed-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6efed-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6efed-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6efed-105">Stosuje operację z możliwością kontrolowania dla klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="6efed-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="6efed-106">Opis</span><span class="sxs-lookup"><span data-stu-id="6efed-106">Description</span></span>

<span data-ttu-id="6efed-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="6efed-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="6efed-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="6efed-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="6efed-109">Sufiks `C` wskazuje, że operacja do zastosowania jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="6efed-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="6efed-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6efed-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="6efed-111">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="6efed-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="6efed-112">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="6efed-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="6efed-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6efed-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6efed-114">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="6efed-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="6efed-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="6efed-115">target : 'T</span></span>

<span data-ttu-id="6efed-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="6efed-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6efed-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6efed-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6efed-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6efed-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6efed-119">'C</span><span class="sxs-lookup"><span data-stu-id="6efed-119">'T</span></span>

<span data-ttu-id="6efed-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="6efed-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="6efed-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6efed-121">See Also</span></span>

- [<span data-ttu-id="6efed-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="6efed-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="6efed-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="6efed-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="6efed-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="6efed-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)