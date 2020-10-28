---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717173"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="55694-102">ApplyToMostC, operacja</span><span class="sxs-lookup"><span data-stu-id="55694-102">ApplyToMostC operation</span></span>

<span data-ttu-id="55694-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="55694-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="55694-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55694-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55694-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="55694-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="55694-106">Opis</span><span class="sxs-lookup"><span data-stu-id="55694-106">Description</span></span>

<span data-ttu-id="55694-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="55694-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="55694-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="55694-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="55694-109">op: t [] => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="55694-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="55694-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="55694-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="55694-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="55694-111">targets : 'T[]</span></span>

<span data-ttu-id="55694-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="55694-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55694-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55694-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="55694-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="55694-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="55694-115">'C</span><span class="sxs-lookup"><span data-stu-id="55694-115">'T</span></span>

<span data-ttu-id="55694-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="55694-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="55694-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="55694-117">See Also</span></span>

- [<span data-ttu-id="55694-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="55694-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="55694-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="55694-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="55694-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="55694-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)