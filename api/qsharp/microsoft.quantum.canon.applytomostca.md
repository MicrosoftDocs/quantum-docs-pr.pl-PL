---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717164"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="aa309-102">ApplyToMostCA, operacja</span><span class="sxs-lookup"><span data-stu-id="aa309-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="aa309-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa309-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa309-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa309-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa309-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="aa309-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="aa309-106">Opis</span><span class="sxs-lookup"><span data-stu-id="aa309-106">Description</span></span>

<span data-ttu-id="aa309-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="aa309-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="aa309-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aa309-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="aa309-109">op: t [] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="aa309-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="aa309-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="aa309-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="aa309-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="aa309-111">targets : 'T[]</span></span>

<span data-ttu-id="aa309-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="aa309-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aa309-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aa309-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aa309-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="aa309-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa309-115">'C</span><span class="sxs-lookup"><span data-stu-id="aa309-115">'T</span></span>

<span data-ttu-id="aa309-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="aa309-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa309-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aa309-117">See Also</span></span>

- [<span data-ttu-id="aa309-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="aa309-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="aa309-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="aa309-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="aa309-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="aa309-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)