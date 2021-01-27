---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: ApplyIfZeroCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 4ed0660e2fe3623d0a8e4e4f3bd0bddb536b7b5c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844877"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="7dadb-102">ApplyIfZeroCA, operacja</span><span class="sxs-lookup"><span data-stu-id="7dadb-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="7dadb-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7dadb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7dadb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7dadb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7dadb-105">Stosuje operację jednostkową warunkową dla klasycznej wartości wynikowej równej zero.</span><span class="sxs-lookup"><span data-stu-id="7dadb-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7dadb-106">Opis</span><span class="sxs-lookup"><span data-stu-id="7dadb-106">Description</span></span>

<span data-ttu-id="7dadb-107">Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `Zero` .</span><span class="sxs-lookup"><span data-stu-id="7dadb-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="7dadb-108">Jeśli `One` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="7dadb-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7dadb-109">Sufiks `CA` wskazuje, że operacja ma zostać zastosowana, jest jednostką (sterowaną i sąsiednią).</span><span class="sxs-lookup"><span data-stu-id="7dadb-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="7dadb-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7dadb-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7dadb-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="7dadb-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="7dadb-112">Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="7dadb-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="7dadb-113">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="7dadb-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7dadb-114">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="7dadb-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="7dadb-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="7dadb-115">target : 'T</span></span>

<span data-ttu-id="7dadb-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="7dadb-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7dadb-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7dadb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7dadb-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7dadb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7dadb-119">'C</span><span class="sxs-lookup"><span data-stu-id="7dadb-119">'T</span></span>

<span data-ttu-id="7dadb-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="7dadb-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dadb-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7dadb-121">See Also</span></span>

- [<span data-ttu-id="7dadb-122">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="7dadb-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="7dadb-123">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="7dadb-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="7dadb-124">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="7dadb-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)