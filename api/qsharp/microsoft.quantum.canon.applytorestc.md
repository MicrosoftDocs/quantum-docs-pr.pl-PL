---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 779c3831b2027a58f97dae9609e96d4d98247da7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208197"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="f177a-102">ApplyToRestC, operacja</span><span class="sxs-lookup"><span data-stu-id="f177a-102">ApplyToRestC operation</span></span>

<span data-ttu-id="f177a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f177a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f177a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f177a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f177a-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="f177a-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="f177a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f177a-106">Description</span></span>

<span data-ttu-id="f177a-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f177a-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f177a-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f177a-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f177a-109">op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="f177a-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f177a-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="f177a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f177a-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="f177a-111">targets : 'T[]</span></span>

<span data-ttu-id="f177a-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="f177a-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f177a-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f177a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f177a-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f177a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f177a-115">'C</span><span class="sxs-lookup"><span data-stu-id="f177a-115">'T</span></span>

<span data-ttu-id="f177a-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="f177a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f177a-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f177a-117">See Also</span></span>

- [<span data-ttu-id="f177a-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="f177a-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="f177a-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="f177a-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="f177a-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="f177a-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)