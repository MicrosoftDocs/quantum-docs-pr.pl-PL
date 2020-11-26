---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 3123c7f7b5e5c7f5cb17a34eedc81b3912109883
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208163"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="e0676-102">ApplyToRestCA, operacja</span><span class="sxs-lookup"><span data-stu-id="e0676-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="e0676-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e0676-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e0676-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0676-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0676-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="e0676-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="e0676-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e0676-106">Description</span></span>

<span data-ttu-id="e0676-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="e0676-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="e0676-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e0676-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="e0676-109">op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="e0676-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e0676-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="e0676-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="e0676-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="e0676-111">targets : 'T[]</span></span>

<span data-ttu-id="e0676-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="e0676-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e0676-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e0676-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e0676-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e0676-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0676-115">'C</span><span class="sxs-lookup"><span data-stu-id="e0676-115">'T</span></span>

<span data-ttu-id="e0676-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="e0676-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0676-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e0676-117">See Also</span></span>

- [<span data-ttu-id="e0676-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="e0676-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="e0676-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="e0676-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="e0676-120">Microsoft. Quantum. Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="e0676-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)