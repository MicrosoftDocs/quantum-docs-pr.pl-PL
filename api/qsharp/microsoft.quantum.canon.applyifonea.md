---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718097"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="aeda0-102">ApplyIfOneA, operacja</span><span class="sxs-lookup"><span data-stu-id="aeda0-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="aeda0-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aeda0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aeda0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aeda0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aeda0-105">Stosuje operację sąsiedniego wyniku dla klasycznej wartości wynikowej.</span><span class="sxs-lookup"><span data-stu-id="aeda0-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="aeda0-106">Opis</span><span class="sxs-lookup"><span data-stu-id="aeda0-106">Description</span></span>

<span data-ttu-id="aeda0-107">Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `One` .</span><span class="sxs-lookup"><span data-stu-id="aeda0-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="aeda0-108">Jeśli `Zero` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="aeda0-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="aeda0-109">Sufiks `A` wskazuje, że operacja, która ma zostać zastosowana, to przylegający.</span><span class="sxs-lookup"><span data-stu-id="aeda0-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="aeda0-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aeda0-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="aeda0-111">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="aeda0-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="aeda0-112">Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="aeda0-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="aeda0-113">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aeda0-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="aeda0-114">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="aeda0-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="aeda0-115">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="aeda0-115">target : 'T</span></span>

<span data-ttu-id="aeda0-116">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="aeda0-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aeda0-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aeda0-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aeda0-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="aeda0-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aeda0-119">'C</span><span class="sxs-lookup"><span data-stu-id="aeda0-119">'T</span></span>

<span data-ttu-id="aeda0-120">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="aeda0-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="aeda0-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aeda0-121">See Also</span></span>

- [<span data-ttu-id="aeda0-122">Microsoft. Quantum. Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="aeda0-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="aeda0-123">Microsoft. Quantum. Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="aeda0-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="aeda0-124">Microsoft. Quantum. Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="aeda0-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)