---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 1bb24006a2d52167dfc7a7871cfbf5a4378d1cb7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850616"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="f7c89-102">ApplyToHeadCA, operacja</span><span class="sxs-lookup"><span data-stu-id="f7c89-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="f7c89-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7c89-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7c89-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f7c89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f7c89-105">Stosuje operację do pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="f7c89-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f7c89-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f7c89-106">Description</span></span>

<span data-ttu-id="f7c89-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="f7c89-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="f7c89-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f7c89-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="f7c89-109">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="f7c89-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="f7c89-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="f7c89-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="f7c89-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="f7c89-111">targets : 'T[]</span></span>

<span data-ttu-id="f7c89-112">Tablica elementów docelowych, do których zostanie zastosowany pierwszy `op` .</span><span class="sxs-lookup"><span data-stu-id="f7c89-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f7c89-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7c89-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f7c89-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f7c89-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7c89-115">'C</span><span class="sxs-lookup"><span data-stu-id="f7c89-115">'T</span></span>

<span data-ttu-id="f7c89-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="f7c89-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7c89-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f7c89-117">See Also</span></span>

- [<span data-ttu-id="f7c89-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="f7c89-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="f7c89-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="f7c89-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="f7c89-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="f7c89-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)