---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717453"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="9a933-102">ApplyToElementC, operacja</span><span class="sxs-lookup"><span data-stu-id="9a933-102">ApplyToElementC operation</span></span>

<span data-ttu-id="9a933-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9a933-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9a933-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a933-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a933-105">Stosuje operację do danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9a933-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9a933-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9a933-106">Description</span></span>

<span data-ttu-id="9a933-107">`op`Mają zastosowanie operacje, indeks `index` i Tablica elementów docelowych `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="9a933-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="9a933-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9a933-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="9a933-109">op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a933-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="9a933-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="9a933-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="9a933-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9a933-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9a933-112">Indeks do tablicy elementów docelowych.</span><span class="sxs-lookup"><span data-stu-id="9a933-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9a933-113">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="9a933-113">targets : 'T[]</span></span>

<span data-ttu-id="9a933-114">Tablica możliwych elementów docelowych dla `op` .</span><span class="sxs-lookup"><span data-stu-id="9a933-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a933-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a933-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9a933-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9a933-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9a933-117">'C</span><span class="sxs-lookup"><span data-stu-id="9a933-117">'T</span></span>

<span data-ttu-id="9a933-118">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="9a933-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a933-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a933-119">See Also</span></span>

- [<span data-ttu-id="9a933-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="9a933-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="9a933-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="9a933-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="9a933-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="9a933-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)