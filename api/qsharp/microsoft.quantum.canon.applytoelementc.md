---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850740"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="be268-102">ApplyToElementC, operacja</span><span class="sxs-lookup"><span data-stu-id="be268-102">ApplyToElementC operation</span></span>

<span data-ttu-id="be268-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="be268-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="be268-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="be268-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="be268-105">Stosuje operację do danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="be268-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="be268-106">Opis</span><span class="sxs-lookup"><span data-stu-id="be268-106">Description</span></span>

<span data-ttu-id="be268-107">`op`Mają zastosowanie operacje, indeks `index` i Tablica elementów docelowych `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="be268-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="be268-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="be268-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="be268-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="be268-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="be268-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="be268-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="be268-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="be268-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="be268-112">Indeks do tablicy elementów docelowych.</span><span class="sxs-lookup"><span data-stu-id="be268-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="be268-113">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="be268-113">targets : 'T[]</span></span>

<span data-ttu-id="be268-114">Tablica możliwych elementów docelowych dla `op` .</span><span class="sxs-lookup"><span data-stu-id="be268-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="be268-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="be268-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="be268-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="be268-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="be268-117">'C</span><span class="sxs-lookup"><span data-stu-id="be268-117">'T</span></span>

<span data-ttu-id="be268-118">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="be268-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="be268-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="be268-119">See Also</span></span>

- [<span data-ttu-id="be268-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="be268-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="be268-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="be268-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="be268-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="be268-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)