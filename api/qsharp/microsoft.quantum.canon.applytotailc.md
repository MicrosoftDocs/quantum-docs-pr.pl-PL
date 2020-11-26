---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5a68cae3fd122416cfd064e0078e03f5c00ab492
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217292"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="620fb-102">ApplyToTailC, operacja</span><span class="sxs-lookup"><span data-stu-id="620fb-102">ApplyToTailC operation</span></span>

<span data-ttu-id="620fb-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="620fb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="620fb-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="620fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="620fb-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="620fb-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="620fb-106">Opis</span><span class="sxs-lookup"><span data-stu-id="620fb-106">Description</span></span>

<span data-ttu-id="620fb-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="620fb-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="620fb-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="620fb-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="620fb-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="620fb-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="620fb-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="620fb-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="620fb-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="620fb-111">targets : 'T[]</span></span>

<span data-ttu-id="620fb-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="620fb-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="620fb-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="620fb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="620fb-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="620fb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="620fb-115">'C</span><span class="sxs-lookup"><span data-stu-id="620fb-115">'T</span></span>

<span data-ttu-id="620fb-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="620fb-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="620fb-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="620fb-117">See Also</span></span>

- [<span data-ttu-id="620fb-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="620fb-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="620fb-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="620fb-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="620fb-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="620fb-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)