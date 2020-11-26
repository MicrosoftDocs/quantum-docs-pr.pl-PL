---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b7c07e01ebcaf2d475283bea0695aa68dd10776e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209404"
---
# <a name="applyifone-operation"></a><span data-ttu-id="b48a5-102">ApplyIfOne, operacja</span><span class="sxs-lookup"><span data-stu-id="b48a5-102">ApplyIfOne operation</span></span>

<span data-ttu-id="b48a5-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b48a5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b48a5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b48a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b48a5-105">Stosuje operację warunkową dla klasycznej wartości wynikowej.</span><span class="sxs-lookup"><span data-stu-id="b48a5-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="b48a5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b48a5-106">Description</span></span>

<span data-ttu-id="b48a5-107">Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `One` .</span><span class="sxs-lookup"><span data-stu-id="b48a5-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="b48a5-108">Jeśli `Zero` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="b48a5-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="b48a5-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b48a5-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b48a5-110">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="b48a5-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="b48a5-111">Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="b48a5-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="b48a5-112">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b48a5-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b48a5-113">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="b48a5-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="b48a5-114">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="b48a5-114">target : 'T</span></span>

<span data-ttu-id="b48a5-115">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="b48a5-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b48a5-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b48a5-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b48a5-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b48a5-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b48a5-118">'C</span><span class="sxs-lookup"><span data-stu-id="b48a5-118">'T</span></span>

<span data-ttu-id="b48a5-119">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="b48a5-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b48a5-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b48a5-120">See Also</span></span>

- [<span data-ttu-id="b48a5-121">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="b48a5-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="b48a5-122">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="b48a5-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="b48a5-123">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="b48a5-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)