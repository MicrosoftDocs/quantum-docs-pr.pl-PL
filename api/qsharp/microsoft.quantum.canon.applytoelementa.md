---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: e8318a7873476ee49d8e1e235e6c917a38ee6200
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208877"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="ff8d2-102">ApplyToElementA, operacja</span><span class="sxs-lookup"><span data-stu-id="ff8d2-102">ApplyToElementA operation</span></span>

<span data-ttu-id="ff8d2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ff8d2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ff8d2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ff8d2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ff8d2-105">Stosuje operację do danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="ff8d2-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="ff8d2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ff8d2-106">Description</span></span>

<span data-ttu-id="ff8d2-107">`op`Mają zastosowanie operacje, indeks `index` i Tablica elementów docelowych `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="ff8d2-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="ff8d2-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ff8d2-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="ff8d2-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="ff8d2-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="ff8d2-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ff8d2-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="ff8d2-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ff8d2-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ff8d2-112">Indeks do tablicy elementów docelowych.</span><span class="sxs-lookup"><span data-stu-id="ff8d2-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ff8d2-113">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="ff8d2-113">targets : 'T[]</span></span>

<span data-ttu-id="ff8d2-114">Tablica możliwych elementów docelowych dla `op` .</span><span class="sxs-lookup"><span data-stu-id="ff8d2-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff8d2-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff8d2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ff8d2-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ff8d2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ff8d2-117">'C</span><span class="sxs-lookup"><span data-stu-id="ff8d2-117">'T</span></span>

<span data-ttu-id="ff8d2-118">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ff8d2-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff8d2-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff8d2-119">See Also</span></span>

- [<span data-ttu-id="ff8d2-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="ff8d2-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="ff8d2-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="ff8d2-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="ff8d2-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="ff8d2-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)