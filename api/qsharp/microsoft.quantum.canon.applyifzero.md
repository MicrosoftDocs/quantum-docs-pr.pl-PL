---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 215b71a8d2e4f8a22df05b210824bc40a969b6f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841746"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="b1185-102">ApplyIfZero, operacja</span><span class="sxs-lookup"><span data-stu-id="b1185-102">ApplyIfZero operation</span></span>

<span data-ttu-id="b1185-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1185-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1185-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1185-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1185-105">Stosuje operację warunkową dla klasycznej wartości wynikowej równej zero.</span><span class="sxs-lookup"><span data-stu-id="b1185-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="b1185-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b1185-106">Description</span></span>

<span data-ttu-id="b1185-107">Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `Zero` .</span><span class="sxs-lookup"><span data-stu-id="b1185-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="b1185-108">Jeśli `One` nie, nic się nie dzieje z `target` .</span><span class="sxs-lookup"><span data-stu-id="b1185-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="b1185-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b1185-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b1185-110">wynik: __nieprawidłowe <Result>__</span><span class="sxs-lookup"><span data-stu-id="b1185-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="b1185-111">Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.</span><span class="sxs-lookup"><span data-stu-id="b1185-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="b1185-112">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="b1185-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b1185-113">Operacja, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="b1185-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="b1185-114">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="b1185-114">target : 'T</span></span>

<span data-ttu-id="b1185-115">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="b1185-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1185-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1185-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1185-117">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b1185-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1185-118">'C</span><span class="sxs-lookup"><span data-stu-id="b1185-118">'T</span></span>

<span data-ttu-id="b1185-119">Typ wejściowy operacji, która ma być stosowana warunkowo.</span><span class="sxs-lookup"><span data-stu-id="b1185-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1185-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1185-120">See Also</span></span>

- [<span data-ttu-id="b1185-121">Microsoft. Quantum. Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="b1185-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="b1185-122">Microsoft. Quantum. Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="b1185-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="b1185-123">Microsoft. Quantum. Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="b1185-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)