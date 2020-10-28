---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 55e534b7b7673f300b607a8213418c45c8c7c92c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717094"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="72913-102">ApplyToRestC, operacja</span><span class="sxs-lookup"><span data-stu-id="72913-102">ApplyToRestC operation</span></span>

<span data-ttu-id="72913-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72913-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72913-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72913-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72913-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="72913-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="72913-106">Opis</span><span class="sxs-lookup"><span data-stu-id="72913-106">Description</span></span>

<span data-ttu-id="72913-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="72913-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="72913-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="72913-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="72913-109">op: t [] => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="72913-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="72913-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="72913-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="72913-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="72913-111">targets : 'T[]</span></span>

<span data-ttu-id="72913-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="72913-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72913-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72913-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72913-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="72913-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72913-115">'C</span><span class="sxs-lookup"><span data-stu-id="72913-115">'T</span></span>

<span data-ttu-id="72913-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="72913-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="72913-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="72913-117">See Also</span></span>

- [<span data-ttu-id="72913-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="72913-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="72913-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="72913-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="72913-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="72913-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)