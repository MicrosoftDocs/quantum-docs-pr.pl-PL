---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208418"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="2e6e0-102">ApplyToMostCA, operacja</span><span class="sxs-lookup"><span data-stu-id="2e6e0-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="2e6e0-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2e6e0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2e6e0-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2e6e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2e6e0-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="2e6e0-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="2e6e0-106">Opis</span><span class="sxs-lookup"><span data-stu-id="2e6e0-106">Description</span></span>

<span data-ttu-id="2e6e0-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="2e6e0-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="2e6e0-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2e6e0-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="2e6e0-109">op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="2e6e0-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="2e6e0-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="2e6e0-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="2e6e0-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="2e6e0-111">targets : 'T[]</span></span>

<span data-ttu-id="2e6e0-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="2e6e0-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e6e0-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e6e0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2e6e0-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2e6e0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2e6e0-115">'C</span><span class="sxs-lookup"><span data-stu-id="2e6e0-115">'T</span></span>

<span data-ttu-id="2e6e0-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="2e6e0-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e6e0-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2e6e0-117">See Also</span></span>

- [<span data-ttu-id="2e6e0-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="2e6e0-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="2e6e0-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="2e6e0-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="2e6e0-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="2e6e0-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)