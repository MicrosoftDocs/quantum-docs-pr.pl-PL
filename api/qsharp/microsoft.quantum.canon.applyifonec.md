---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 9a2e020c596b02d9cb38309d02ca02056c1dec75
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718088"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="3908a-102">ApplyIfOneC, operacja</span><span class="sxs-lookup"><span data-stu-id="3908a-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="3908a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3908a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3908a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3908a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3908a-105">Stosuje operację z możliwością kontrolowania dla klasycznej wartości wynikowej.</span><span class="sxs-lookup"><span data-stu-id="3908a-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="3908a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="3908a-106">Description</span></span>

<span data-ttu-id="3908a-107">Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `One` .</span><span class="sxs-lookup"><span data-stu-id="3908a-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="3908a-108">Jeśli `Zero` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="3908a-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3908a-109">Sufiks `C` wskazuje, że operacja do zastosowania jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="3908a-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="3908a-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3908a-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3908a-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="3908a-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="3908a-112">Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="3908a-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="3908a-113">op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3908a-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="3908a-114">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="3908a-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3908a-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="3908a-115">target : 'T</span></span>

<span data-ttu-id="3908a-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="3908a-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3908a-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3908a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3908a-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3908a-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3908a-119">'C</span><span class="sxs-lookup"><span data-stu-id="3908a-119">'T</span></span>

<span data-ttu-id="3908a-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="3908a-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3908a-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3908a-121">See Also</span></span>

- [<span data-ttu-id="3908a-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="3908a-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="3908a-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="3908a-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="3908a-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="3908a-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)