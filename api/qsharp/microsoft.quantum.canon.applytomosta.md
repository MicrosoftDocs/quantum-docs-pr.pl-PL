---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7c226de9b2c99d124c467175dfe65a60a89d4332
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208503"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="cf3ba-102">ApplyToMostA, operacja</span><span class="sxs-lookup"><span data-stu-id="cf3ba-102">ApplyToMostA operation</span></span>

<span data-ttu-id="cf3ba-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cf3ba-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cf3ba-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cf3ba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cf3ba-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="cf3ba-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="cf3ba-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cf3ba-106">Description</span></span>

<span data-ttu-id="cf3ba-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="cf3ba-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="cf3ba-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cf3ba-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="cf3ba-109">op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą</span><span class="sxs-lookup"><span data-stu-id="cf3ba-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="cf3ba-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="cf3ba-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="cf3ba-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="cf3ba-111">targets : 'T[]</span></span>

<span data-ttu-id="cf3ba-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="cf3ba-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf3ba-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf3ba-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cf3ba-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cf3ba-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cf3ba-115">'C</span><span class="sxs-lookup"><span data-stu-id="cf3ba-115">'T</span></span>

<span data-ttu-id="cf3ba-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="cf3ba-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf3ba-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cf3ba-117">See Also</span></span>

- [<span data-ttu-id="cf3ba-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="cf3ba-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="cf3ba-119">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="cf3ba-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="cf3ba-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="cf3ba-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)