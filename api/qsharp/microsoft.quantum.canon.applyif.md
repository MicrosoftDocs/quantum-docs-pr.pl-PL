---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c5a1012328fa012ee02707aa59c94ac9c44b8e87
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218839"
---
# <a name="applyif-operation"></a><span data-ttu-id="217f1-102">ApplyIf, operacja</span><span class="sxs-lookup"><span data-stu-id="217f1-102">ApplyIf operation</span></span>

<span data-ttu-id="217f1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="217f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="217f1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="217f1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="217f1-105">Stosuje operację warunkową przy użyciu klasycznego bitu.</span><span class="sxs-lookup"><span data-stu-id="217f1-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="217f1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="217f1-106">Description</span></span>

<span data-ttu-id="217f1-107">Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` .</span><span class="sxs-lookup"><span data-stu-id="217f1-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="217f1-108">Jeśli `false` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="217f1-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="217f1-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="217f1-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="217f1-110">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="217f1-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="217f1-111">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="217f1-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="217f1-112">bit: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="217f1-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="217f1-113">wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="217f1-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="217f1-114">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="217f1-114">target : 'T</span></span>

<span data-ttu-id="217f1-115">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="217f1-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="217f1-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="217f1-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="217f1-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="217f1-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="217f1-118">'C</span><span class="sxs-lookup"><span data-stu-id="217f1-118">'T</span></span>

<span data-ttu-id="217f1-119">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="217f1-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="217f1-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="217f1-120">See Also</span></span>

- [<span data-ttu-id="217f1-121">Microsoft. Quantum. Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="217f1-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="217f1-122">Microsoft. Quantum. Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="217f1-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="217f1-123">Microsoft. Quantum. Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="217f1-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)