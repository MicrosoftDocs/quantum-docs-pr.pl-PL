---
uid: Microsoft.Quantum.Canon.ApplyToElementA
title: ApplyToElementA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: f34089c2a45de281507cb79bde8a8cb9d2fefe47
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717486"
---
# <a name="applytoelementa-operation"></a><span data-ttu-id="c8f0e-102">ApplyToElementA, operacja</span><span class="sxs-lookup"><span data-stu-id="c8f0e-102">ApplyToElementA operation</span></span>

<span data-ttu-id="c8f0e-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c8f0e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c8f0e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8f0e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8f0e-105">Stosuje operację do danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementA<'T> (op : ('T => Unit is Adj), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="c8f0e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="c8f0e-106">Description</span></span>

<span data-ttu-id="c8f0e-107">`op`Mają zastosowanie operacje, indeks `index` i Tablica elementów docelowych `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="c8f0e-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="c8f0e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c8f0e-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="c8f0e-109">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8f0e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="c8f0e-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="c8f0e-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c8f0e-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c8f0e-112">Indeks do tablicy elementów docelowych.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c8f0e-113">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="c8f0e-113">targets : 'T[]</span></span>

<span data-ttu-id="c8f0e-114">Tablica możliwych elementów docelowych dla `op` .</span><span class="sxs-lookup"><span data-stu-id="c8f0e-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c8f0e-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c8f0e-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c8f0e-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="c8f0e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8f0e-117">'C</span><span class="sxs-lookup"><span data-stu-id="c8f0e-117">'T</span></span>

<span data-ttu-id="c8f0e-118">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="c8f0e-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8f0e-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c8f0e-119">See Also</span></span>

- [<span data-ttu-id="c8f0e-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="c8f0e-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="c8f0e-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="c8f0e-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="c8f0e-122">Microsoft. Quantum. Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="c8f0e-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)