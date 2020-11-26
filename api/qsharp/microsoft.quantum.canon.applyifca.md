---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209625"
---
# <a name="applyifca-operation"></a><span data-ttu-id="c3dfd-102">ApplyIfCA, operacja</span><span class="sxs-lookup"><span data-stu-id="c3dfd-102">ApplyIfCA operation</span></span>

<span data-ttu-id="c3dfd-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c3dfd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c3dfd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3dfd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3dfd-105">Stosuje operacje jednostkowe z zastosowaniem klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="c3dfd-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="c3dfd-106">Opis</span><span class="sxs-lookup"><span data-stu-id="c3dfd-106">Description</span></span>

<span data-ttu-id="c3dfd-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="c3dfd-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="c3dfd-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="c3dfd-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="c3dfd-109">Sufiks `CA` wskazuje, że operacja ma zostać zastosowana, jest jednostką (sterowaną i sąsiednią).</span><span class="sxs-lookup"><span data-stu-id="c3dfd-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="c3dfd-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c3dfd-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="c3dfd-111">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="c3dfd-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c3dfd-112">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="c3dfd-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="c3dfd-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c3dfd-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c3dfd-114">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="c3dfd-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="c3dfd-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="c3dfd-115">target : 'T</span></span>

<span data-ttu-id="c3dfd-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="c3dfd-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3dfd-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3dfd-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c3dfd-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c3dfd-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c3dfd-119">'C</span><span class="sxs-lookup"><span data-stu-id="c3dfd-119">'T</span></span>

<span data-ttu-id="c3dfd-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="c3dfd-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3dfd-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c3dfd-121">See Also</span></span>

- [<span data-ttu-id="c3dfd-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="c3dfd-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="c3dfd-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="c3dfd-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="c3dfd-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="c3dfd-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)