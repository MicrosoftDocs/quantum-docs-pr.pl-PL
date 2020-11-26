---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207976"
---
# <a name="applytotail-operation"></a><span data-ttu-id="02aa6-102">ApplyToTail, operacja</span><span class="sxs-lookup"><span data-stu-id="02aa6-102">ApplyToTail operation</span></span>

<span data-ttu-id="02aa6-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02aa6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02aa6-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="02aa6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="02aa6-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="02aa6-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="02aa6-106">Opis</span><span class="sxs-lookup"><span data-stu-id="02aa6-106">Description</span></span>

<span data-ttu-id="02aa6-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="02aa6-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="02aa6-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="02aa6-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="02aa6-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="02aa6-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="02aa6-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="02aa6-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="02aa6-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="02aa6-111">targets : 'T[]</span></span>

<span data-ttu-id="02aa6-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="02aa6-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="02aa6-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02aa6-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="02aa6-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="02aa6-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02aa6-115">'C</span><span class="sxs-lookup"><span data-stu-id="02aa6-115">'T</span></span>

<span data-ttu-id="02aa6-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="02aa6-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="02aa6-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="02aa6-117">See Also</span></span>

- [<span data-ttu-id="02aa6-118">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="02aa6-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="02aa6-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="02aa6-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="02aa6-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="02aa6-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)