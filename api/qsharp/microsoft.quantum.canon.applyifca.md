---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: 9057c79622f15a082963d94fc261664e00322feb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718233"
---
# <a name="applyifca-operation"></a><span data-ttu-id="4da28-102">ApplyIfCA, operacja</span><span class="sxs-lookup"><span data-stu-id="4da28-102">ApplyIfCA operation</span></span>

<span data-ttu-id="4da28-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4da28-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4da28-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4da28-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4da28-105">Stosuje operacje jednostkowe z zastosowaniem klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="4da28-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="4da28-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4da28-106">Description</span></span>

<span data-ttu-id="4da28-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="4da28-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="4da28-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="4da28-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="4da28-109">Sufiks `CA` wskazuje, że operacja ma zostać zastosowana, jest jednostką (sterowaną i sąsiednią).</span><span class="sxs-lookup"><span data-stu-id="4da28-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="4da28-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4da28-110">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="4da28-111">op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik</span><span class="sxs-lookup"><span data-stu-id="4da28-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="4da28-112">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="4da28-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="4da28-113">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4da28-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4da28-114">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="4da28-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="4da28-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="4da28-115">target : 'T</span></span>

<span data-ttu-id="4da28-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="4da28-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4da28-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4da28-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4da28-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4da28-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4da28-119">'C</span><span class="sxs-lookup"><span data-stu-id="4da28-119">'T</span></span>

<span data-ttu-id="4da28-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="4da28-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4da28-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4da28-121">See Also</span></span>

- [<span data-ttu-id="4da28-122">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="4da28-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="4da28-123">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="4da28-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="4da28-124">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="4da28-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)