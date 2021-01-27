---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5159eee07f7398cc6194c9907a37b78a63aaf263
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850776"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="e71ee-102">ApplyToElement, operacja</span><span class="sxs-lookup"><span data-stu-id="e71ee-102">ApplyToElement operation</span></span>

<span data-ttu-id="e71ee-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e71ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e71ee-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e71ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e71ee-105">Stosuje operację do danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="e71ee-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="e71ee-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e71ee-106">Description</span></span>

<span data-ttu-id="e71ee-107">`op`Mają zastosowanie operacje, indeks `index` i Tablica elementów docelowych `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="e71ee-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="e71ee-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e71ee-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="e71ee-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="e71ee-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e71ee-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="e71ee-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="e71ee-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e71ee-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e71ee-112">Indeks do tablicy elementów docelowych.</span><span class="sxs-lookup"><span data-stu-id="e71ee-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e71ee-113">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="e71ee-113">targets : 'T[]</span></span>

<span data-ttu-id="e71ee-114">Tablica możliwych elementów docelowych dla `op` .</span><span class="sxs-lookup"><span data-stu-id="e71ee-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e71ee-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e71ee-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e71ee-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e71ee-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e71ee-117">'C</span><span class="sxs-lookup"><span data-stu-id="e71ee-117">'T</span></span>

<span data-ttu-id="e71ee-118">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="e71ee-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e71ee-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e71ee-119">See Also</span></span>

- [<span data-ttu-id="e71ee-120">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="e71ee-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="e71ee-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="e71ee-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="e71ee-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="e71ee-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)