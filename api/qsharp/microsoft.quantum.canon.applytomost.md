---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850590"
---
# <a name="applytomost-operation"></a><span data-ttu-id="59a81-102">ApplyToMost, operacja</span><span class="sxs-lookup"><span data-stu-id="59a81-102">ApplyToMost operation</span></span>

<span data-ttu-id="59a81-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="59a81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="59a81-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59a81-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59a81-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="59a81-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="59a81-106">Opis</span><span class="sxs-lookup"><span data-stu-id="59a81-106">Description</span></span>

<span data-ttu-id="59a81-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="59a81-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="59a81-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="59a81-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="59a81-109">op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="59a81-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="59a81-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="59a81-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="59a81-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="59a81-111">targets : 'T[]</span></span>

<span data-ttu-id="59a81-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="59a81-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="59a81-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="59a81-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="59a81-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="59a81-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59a81-115">'C</span><span class="sxs-lookup"><span data-stu-id="59a81-115">'T</span></span>

<span data-ttu-id="59a81-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="59a81-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="59a81-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="59a81-117">Example</span></span>

<span data-ttu-id="59a81-118">Następujące fragmenty kodu Q # są równoważne:</span><span class="sxs-lookup"><span data-stu-id="59a81-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="59a81-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="59a81-119">See Also</span></span>

- [<span data-ttu-id="59a81-120">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="59a81-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="59a81-121">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="59a81-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="59a81-122">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="59a81-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)