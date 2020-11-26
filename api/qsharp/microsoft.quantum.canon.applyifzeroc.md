---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: c89490b13d946d119f3fd38d130d90847d67fea6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209353"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="dac84-102">ApplyIfZeroC, operacja</span><span class="sxs-lookup"><span data-stu-id="dac84-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="dac84-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dac84-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dac84-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dac84-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dac84-105">Stosuje operację z możliwością kontrolowania, która jest zależna od wartości wyniku klasycznego.</span><span class="sxs-lookup"><span data-stu-id="dac84-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="dac84-106">Opis</span><span class="sxs-lookup"><span data-stu-id="dac84-106">Description</span></span>

<span data-ttu-id="dac84-107">Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `Zero` .</span><span class="sxs-lookup"><span data-stu-id="dac84-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="dac84-108">Jeśli `One` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="dac84-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="dac84-109">Sufiks `C` wskazuje, że operacja do zastosowania jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="dac84-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="dac84-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="dac84-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="dac84-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="dac84-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="dac84-112">Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="dac84-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="dac84-113">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="dac84-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="dac84-114">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="dac84-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="dac84-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="dac84-115">target : 'T</span></span>

<span data-ttu-id="dac84-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="dac84-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dac84-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dac84-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dac84-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="dac84-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dac84-119">'C</span><span class="sxs-lookup"><span data-stu-id="dac84-119">'T</span></span>

<span data-ttu-id="dac84-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="dac84-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="dac84-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dac84-121">See Also</span></span>

- [<span data-ttu-id="dac84-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="dac84-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="dac84-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="dac84-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="dac84-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="dac84-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)