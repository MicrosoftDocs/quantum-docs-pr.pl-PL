---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841197"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="56c75-102">ApplyToTailCA, operacja</span><span class="sxs-lookup"><span data-stu-id="56c75-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="56c75-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="56c75-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="56c75-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="56c75-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="56c75-105">Stosuje operację do ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="56c75-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="56c75-106">Opis</span><span class="sxs-lookup"><span data-stu-id="56c75-106">Description</span></span>

<span data-ttu-id="56c75-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Tail(targets))` .</span><span class="sxs-lookup"><span data-stu-id="56c75-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="56c75-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="56c75-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="56c75-109">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="56c75-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="56c75-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="56c75-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="56c75-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="56c75-111">targets : 'T[]</span></span>

<span data-ttu-id="56c75-112">Tablica elementów docelowych, do których zostanie zastosowana Ostatnia `op` .</span><span class="sxs-lookup"><span data-stu-id="56c75-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56c75-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56c75-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="56c75-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="56c75-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="56c75-115">'C</span><span class="sxs-lookup"><span data-stu-id="56c75-115">'T</span></span>

<span data-ttu-id="56c75-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="56c75-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="56c75-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="56c75-117">See Also</span></span>

- [<span data-ttu-id="56c75-118">Microsoft. Quantum. Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="56c75-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="56c75-119">Microsoft. Quantum. Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="56c75-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="56c75-120">Microsoft. Quantum. Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="56c75-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)