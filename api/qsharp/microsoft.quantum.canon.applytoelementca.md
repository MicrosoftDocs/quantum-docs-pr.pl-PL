---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 420a92ae10d2fc260024968b1846e669c4b62d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841467"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="4593c-102">ApplyToElementCA, operacja</span><span class="sxs-lookup"><span data-stu-id="4593c-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="4593c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4593c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4593c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4593c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4593c-105">Stosuje operację do danego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="4593c-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4593c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4593c-106">Description</span></span>

<span data-ttu-id="4593c-107">`op`Mają zastosowanie operacje, indeks `index` i Tablica elementów docelowych `targets` `op(targets[index])` .</span><span class="sxs-lookup"><span data-stu-id="4593c-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="4593c-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4593c-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="4593c-109">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="4593c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="4593c-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4593c-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="4593c-111">indeks: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4593c-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4593c-112">Indeks do tablicy elementów docelowych.</span><span class="sxs-lookup"><span data-stu-id="4593c-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4593c-113">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="4593c-113">targets : 'T[]</span></span>

<span data-ttu-id="4593c-114">Tablica możliwych elementów docelowych dla `op` .</span><span class="sxs-lookup"><span data-stu-id="4593c-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4593c-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4593c-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4593c-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4593c-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4593c-117">'C</span><span class="sxs-lookup"><span data-stu-id="4593c-117">'T</span></span>

<span data-ttu-id="4593c-118">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4593c-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4593c-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4593c-119">See Also</span></span>

- [<span data-ttu-id="4593c-120">Microsoft. Quantum. Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="4593c-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="4593c-121">Microsoft. Quantum. Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="4593c-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="4593c-122">Microsoft. Quantum. Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="4593c-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)