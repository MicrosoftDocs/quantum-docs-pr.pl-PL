---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717229"
---
# <a name="applytomost-operation"></a><span data-ttu-id="4faf5-102">ApplyToMost, operacja</span><span class="sxs-lookup"><span data-stu-id="4faf5-102">ApplyToMost operation</span></span>

<span data-ttu-id="4faf5-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4faf5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4faf5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4faf5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4faf5-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="4faf5-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4faf5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4faf5-106">Description</span></span>

<span data-ttu-id="4faf5-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="4faf5-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="4faf5-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4faf5-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4faf5-109">op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4faf5-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4faf5-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4faf5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4faf5-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="4faf5-111">targets : 'T[]</span></span>

<span data-ttu-id="4faf5-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="4faf5-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4faf5-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4faf5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4faf5-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4faf5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4faf5-115">'C</span><span class="sxs-lookup"><span data-stu-id="4faf5-115">'T</span></span>

<span data-ttu-id="4faf5-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4faf5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4faf5-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4faf5-117">See Also</span></span>

- [<span data-ttu-id="4faf5-118">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="4faf5-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="4faf5-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="4faf5-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="4faf5-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="4faf5-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)