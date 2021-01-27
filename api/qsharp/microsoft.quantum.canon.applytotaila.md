---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5ca22be7a38d466f9413977de663f10606171dea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841184"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="b5af9-102">ApplyToTailA, operacja</span><span class="sxs-lookup"><span data-stu-id="b5af9-102">ApplyToTailA operation</span></span>

<span data-ttu-id="b5af9-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b5af9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b5af9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b5af9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b5af9-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="b5af9-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b5af9-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b5af9-106">Description</span></span>

<span data-ttu-id="b5af9-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="b5af9-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b5af9-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b5af9-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="b5af9-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="b5af9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b5af9-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b5af9-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b5af9-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="b5af9-111">targets : 'T[]</span></span>

<span data-ttu-id="b5af9-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="b5af9-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b5af9-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b5af9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b5af9-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b5af9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b5af9-115">'C</span><span class="sxs-lookup"><span data-stu-id="b5af9-115">'T</span></span>

<span data-ttu-id="b5af9-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b5af9-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b5af9-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b5af9-117">See Also</span></span>

- [<span data-ttu-id="b5af9-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="b5af9-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="b5af9-119">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="b5af9-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="b5af9-120">Microsoft. Quantum. Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="b5af9-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)