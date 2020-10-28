---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717509"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="cdfe5-102">ApplyToElement, operacja</span><span class="sxs-lookup"><span data-stu-id="cdfe5-102">ApplyToElement operation</span></span>

<span data-ttu-id="cdfe5-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cdfe5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cdfe5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cdfe5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cdfe5-105">Stosuje operację do danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="cdfe5-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="cdfe5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cdfe5-106">Description</span></span>

<span data-ttu-id="cdfe5-107">`op`Mają zastosowanie operacje, indeks `index` i Tablica elementów docelowych `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="cdfe5-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="cdfe5-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cdfe5-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="cdfe5-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="cdfe5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cdfe5-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="cdfe5-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="cdfe5-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cdfe5-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cdfe5-112">Indeks do tablicy elementów docelowych.</span><span class="sxs-lookup"><span data-stu-id="cdfe5-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="cdfe5-113">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="cdfe5-113">targets : 'T[]</span></span>

<span data-ttu-id="cdfe5-114">Tablica możliwych elementów docelowych dla `op` .</span><span class="sxs-lookup"><span data-stu-id="cdfe5-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cdfe5-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cdfe5-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cdfe5-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cdfe5-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cdfe5-117">'C</span><span class="sxs-lookup"><span data-stu-id="cdfe5-117">'T</span></span>

<span data-ttu-id="cdfe5-118">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="cdfe5-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cdfe5-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cdfe5-119">See Also</span></span>

- [<span data-ttu-id="cdfe5-120">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="cdfe5-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="cdfe5-121">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="cdfe5-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="cdfe5-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="cdfe5-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)