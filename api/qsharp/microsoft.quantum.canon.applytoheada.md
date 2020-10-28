---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717257"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="23b3b-102">ApplyToHeadA, operacja</span><span class="sxs-lookup"><span data-stu-id="23b3b-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="23b3b-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="23b3b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="23b3b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="23b3b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="23b3b-105">Stosuje operację do pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="23b3b-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="23b3b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="23b3b-106">Description</span></span>

<span data-ttu-id="23b3b-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="23b3b-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="23b3b-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="23b3b-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="23b3b-109">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23b3b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="23b3b-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="23b3b-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="23b3b-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="23b3b-111">targets : 'T[]</span></span>

<span data-ttu-id="23b3b-112">Tablica elementów docelowych, do których zostanie zastosowany pierwszy `op` .</span><span class="sxs-lookup"><span data-stu-id="23b3b-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="23b3b-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="23b3b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="23b3b-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="23b3b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23b3b-115">'C</span><span class="sxs-lookup"><span data-stu-id="23b3b-115">'T</span></span>

<span data-ttu-id="23b3b-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="23b3b-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="23b3b-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="23b3b-117">See Also</span></span>

- [<span data-ttu-id="23b3b-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="23b3b-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="23b3b-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="23b3b-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="23b3b-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="23b3b-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)