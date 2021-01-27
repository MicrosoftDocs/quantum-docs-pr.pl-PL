---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 0a80c23e0c6ff45083c192579dd8301d2277cef2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841314"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="33510-102">ApplyToMostCA, operacja</span><span class="sxs-lookup"><span data-stu-id="33510-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="33510-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="33510-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="33510-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="33510-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="33510-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="33510-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="33510-106">Opis</span><span class="sxs-lookup"><span data-stu-id="33510-106">Description</span></span>

<span data-ttu-id="33510-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="33510-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="33510-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="33510-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="33510-109">op: t [] => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="33510-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="33510-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="33510-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="33510-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="33510-111">targets : 'T[]</span></span>

<span data-ttu-id="33510-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="33510-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="33510-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="33510-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="33510-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="33510-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="33510-115">'C</span><span class="sxs-lookup"><span data-stu-id="33510-115">'T</span></span>

<span data-ttu-id="33510-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="33510-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="33510-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="33510-117">See Also</span></span>

- [<span data-ttu-id="33510-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="33510-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="33510-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="33510-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="33510-120">Microsoft. Quantum. Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="33510-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)