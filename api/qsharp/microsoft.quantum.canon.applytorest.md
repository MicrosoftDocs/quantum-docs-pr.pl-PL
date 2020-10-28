---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 29bf080d693c668421181f10faef50f5681683be
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717108"
---
# <a name="applytorest-operation"></a><span data-ttu-id="ff3cc-102">ApplyToRest, operacja</span><span class="sxs-lookup"><span data-stu-id="ff3cc-102">ApplyToRest operation</span></span>

<span data-ttu-id="ff3cc-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ff3cc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ff3cc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ff3cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ff3cc-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="ff3cc-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="ff3cc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="ff3cc-106">Description</span></span>

<span data-ttu-id="ff3cc-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="ff3cc-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ff3cc-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ff3cc-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="ff3cc-109">op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="ff3cc-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ff3cc-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ff3cc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ff3cc-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="ff3cc-111">targets : 'T[]</span></span>

<span data-ttu-id="ff3cc-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="ff3cc-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ff3cc-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ff3cc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ff3cc-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ff3cc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ff3cc-115">'C</span><span class="sxs-lookup"><span data-stu-id="ff3cc-115">'T</span></span>

<span data-ttu-id="ff3cc-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ff3cc-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff3cc-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ff3cc-117">See Also</span></span>

- [<span data-ttu-id="ff3cc-118">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="ff3cc-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="ff3cc-119">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="ff3cc-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="ff3cc-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="ff3cc-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)