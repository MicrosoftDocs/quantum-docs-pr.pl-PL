---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: d2dc10803044980d53f80f0577d16cb14a2eb301
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717066"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="07421-102">ApplyToRestCA, operacja</span><span class="sxs-lookup"><span data-stu-id="07421-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="07421-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="07421-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="07421-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07421-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07421-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="07421-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="07421-106">Opis</span><span class="sxs-lookup"><span data-stu-id="07421-106">Description</span></span>

<span data-ttu-id="07421-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="07421-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="07421-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="07421-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="07421-109">op: t [] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="07421-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="07421-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="07421-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="07421-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="07421-111">targets : 'T[]</span></span>

<span data-ttu-id="07421-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="07421-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="07421-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="07421-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="07421-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="07421-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="07421-115">'C</span><span class="sxs-lookup"><span data-stu-id="07421-115">'T</span></span>

<span data-ttu-id="07421-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="07421-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="07421-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="07421-117">See Also</span></span>

- [<span data-ttu-id="07421-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="07421-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="07421-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="07421-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="07421-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="07421-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)