---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 290347ff54492c4291db540e82cedcdd822a354e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850639"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="357a1-102">ApplyToHeadA, operacja</span><span class="sxs-lookup"><span data-stu-id="357a1-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="357a1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="357a1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="357a1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="357a1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="357a1-105">Stosuje operację do pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="357a1-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="357a1-106">Opis</span><span class="sxs-lookup"><span data-stu-id="357a1-106">Description</span></span>

<span data-ttu-id="357a1-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="357a1-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="357a1-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="357a1-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="357a1-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="357a1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="357a1-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="357a1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="357a1-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="357a1-111">targets : 'T[]</span></span>

<span data-ttu-id="357a1-112">Tablica elementów docelowych, do których zostanie zastosowany pierwszy `op` .</span><span class="sxs-lookup"><span data-stu-id="357a1-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="357a1-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="357a1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="357a1-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="357a1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="357a1-115">'C</span><span class="sxs-lookup"><span data-stu-id="357a1-115">'T</span></span>

<span data-ttu-id="357a1-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="357a1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="357a1-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="357a1-117">See Also</span></span>

- [<span data-ttu-id="357a1-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="357a1-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="357a1-119">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="357a1-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="357a1-120">Microsoft. Quantum. Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="357a1-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)