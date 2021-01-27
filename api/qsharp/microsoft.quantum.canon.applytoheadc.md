---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3a65ad52e0b2f8b3a921fc549c35311f24d0e189
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850627"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="8fefd-102">ApplyToHeadC, operacja</span><span class="sxs-lookup"><span data-stu-id="8fefd-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="8fefd-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8fefd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8fefd-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8fefd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8fefd-105">Stosuje operację do pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="8fefd-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="8fefd-106">Opis</span><span class="sxs-lookup"><span data-stu-id="8fefd-106">Description</span></span>

<span data-ttu-id="8fefd-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="8fefd-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="8fefd-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8fefd-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="8fefd-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="8fefd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8fefd-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="8fefd-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="8fefd-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="8fefd-111">targets : 'T[]</span></span>

<span data-ttu-id="8fefd-112">Tablica elementów docelowych, do których zostanie zastosowany pierwszy `op` .</span><span class="sxs-lookup"><span data-stu-id="8fefd-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8fefd-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8fefd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8fefd-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8fefd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8fefd-115">'C</span><span class="sxs-lookup"><span data-stu-id="8fefd-115">'T</span></span>

<span data-ttu-id="8fefd-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="8fefd-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fefd-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8fefd-117">See Also</span></span>

- [<span data-ttu-id="8fefd-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="8fefd-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="8fefd-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="8fefd-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="8fefd-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="8fefd-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)