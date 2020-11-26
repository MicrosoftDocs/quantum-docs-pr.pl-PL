---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: afb9eaa277814d7434b00a5c853a0c002190c1ae
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207857"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="9b32a-102">ApplyToTailCA, operacja</span><span class="sxs-lookup"><span data-stu-id="9b32a-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="9b32a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b32a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b32a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b32a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b32a-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="9b32a-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="9b32a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="9b32a-106">Description</span></span>

<span data-ttu-id="9b32a-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="9b32a-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="9b32a-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9b32a-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="9b32a-109">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="9b32a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9b32a-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="9b32a-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9b32a-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="9b32a-111">targets : 'T[]</span></span>

<span data-ttu-id="9b32a-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="9b32a-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b32a-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b32a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9b32a-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9b32a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9b32a-115">'C</span><span class="sxs-lookup"><span data-stu-id="9b32a-115">'T</span></span>

<span data-ttu-id="9b32a-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="9b32a-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b32a-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9b32a-117">See Also</span></span>

- [<span data-ttu-id="9b32a-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="9b32a-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="9b32a-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="9b32a-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="9b32a-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="9b32a-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)