---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718245"
---
# <a name="applyif-operation"></a><span data-ttu-id="921cc-102">ApplyIf, operacja</span><span class="sxs-lookup"><span data-stu-id="921cc-102">ApplyIf operation</span></span>

<span data-ttu-id="921cc-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="921cc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="921cc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="921cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="921cc-105">Stosuje operację warunkową przy użyciu klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="921cc-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="921cc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="921cc-106">Description</span></span>

<span data-ttu-id="921cc-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="921cc-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="921cc-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="921cc-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="921cc-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="921cc-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="921cc-110">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="921cc-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="921cc-111">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="921cc-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="921cc-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="921cc-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="921cc-113">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="921cc-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="921cc-114">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="921cc-114">target : 'T</span></span>

<span data-ttu-id="921cc-115">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="921cc-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="921cc-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="921cc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="921cc-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="921cc-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="921cc-118">'C</span><span class="sxs-lookup"><span data-stu-id="921cc-118">'T</span></span>

<span data-ttu-id="921cc-119">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="921cc-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="921cc-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="921cc-120">See Also</span></span>

- [<span data-ttu-id="921cc-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="921cc-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="921cc-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="921cc-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="921cc-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="921cc-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)