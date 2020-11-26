---
uid: Microsoft.Quantum.Canon.ApplyToHead
title: ApplyToHead, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHead
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 35f19cbb1090e974e18f338239764c9c8b854116
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217343"
---
# <a name="applytohead-operation"></a><span data-ttu-id="d5f60-102">ApplyToHead, operacja</span><span class="sxs-lookup"><span data-stu-id="d5f60-102">ApplyToHead operation</span></span>

<span data-ttu-id="d5f60-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5f60-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5f60-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5f60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5f60-105">Stosuje operację do pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="d5f60-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHead<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d5f60-106">Opis</span><span class="sxs-lookup"><span data-stu-id="d5f60-106">Description</span></span>

<span data-ttu-id="d5f60-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="d5f60-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d5f60-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d5f60-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="d5f60-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="d5f60-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d5f60-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="d5f60-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d5f60-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="d5f60-111">targets : 'T[]</span></span>

<span data-ttu-id="d5f60-112">Tablica elementów docelowych, do których zostanie zastosowany pierwszy `op` .</span><span class="sxs-lookup"><span data-stu-id="d5f60-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5f60-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5f60-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d5f60-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d5f60-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5f60-115">'C</span><span class="sxs-lookup"><span data-stu-id="d5f60-115">'T</span></span>

<span data-ttu-id="d5f60-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="d5f60-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5f60-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d5f60-117">See Also</span></span>

- [<span data-ttu-id="d5f60-118">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="d5f60-118">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="d5f60-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="d5f60-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="d5f60-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="d5f60-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)