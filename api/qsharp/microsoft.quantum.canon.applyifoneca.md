---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 8b27a192c66a127fe5a8acfbba7b78314988bf2e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844910"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="58ceb-102">ApplyIfOneCA, operacja</span><span class="sxs-lookup"><span data-stu-id="58ceb-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="58ceb-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="58ceb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="58ceb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58ceb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58ceb-105">Stosuje operację jednostkową warunkową dla klasycznej wartości wynikowej.</span><span class="sxs-lookup"><span data-stu-id="58ceb-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="58ceb-106">Opis</span><span class="sxs-lookup"><span data-stu-id="58ceb-106">Description</span></span>

<span data-ttu-id="58ceb-107">Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `One` .</span><span class="sxs-lookup"><span data-stu-id="58ceb-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="58ceb-108">Jeśli `Zero` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="58ceb-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="58ceb-109">Sufiks `CA` wskazuje, że operacja ma zostać zastosowana, jest jednostką (sterowaną i sąsiednią).</span><span class="sxs-lookup"><span data-stu-id="58ceb-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="58ceb-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="58ceb-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="58ceb-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="58ceb-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="58ceb-112">Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="58ceb-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="58ceb-113">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="58ceb-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="58ceb-114">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="58ceb-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="58ceb-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="58ceb-115">target : 'T</span></span>

<span data-ttu-id="58ceb-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="58ceb-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58ceb-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58ceb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="58ceb-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="58ceb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58ceb-119">'C</span><span class="sxs-lookup"><span data-stu-id="58ceb-119">'T</span></span>

<span data-ttu-id="58ceb-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="58ceb-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="58ceb-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="58ceb-121">See Also</span></span>

- [<span data-ttu-id="58ceb-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="58ceb-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="58ceb-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="58ceb-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="58ceb-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="58ceb-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)