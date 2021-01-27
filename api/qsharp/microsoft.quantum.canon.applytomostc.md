---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850561"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="11edc-102">ApplyToMostC, operacja</span><span class="sxs-lookup"><span data-stu-id="11edc-102">ApplyToMostC operation</span></span>

<span data-ttu-id="11edc-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="11edc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="11edc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11edc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11edc-105">Stosuje operację do wszystkich elementów oprócz ostatniego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="11edc-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="11edc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="11edc-106">Description</span></span>

<span data-ttu-id="11edc-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Most(targets))` .</span><span class="sxs-lookup"><span data-stu-id="11edc-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="11edc-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="11edc-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="11edc-109">op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="11edc-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="11edc-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="11edc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="11edc-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="11edc-111">targets : 'T[]</span></span>

<span data-ttu-id="11edc-112">Tablica elementów docelowych, do których zostaną zastosowane wszystkie, ale tylko ostatnie `op` .</span><span class="sxs-lookup"><span data-stu-id="11edc-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="11edc-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11edc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="11edc-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="11edc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="11edc-115">'C</span><span class="sxs-lookup"><span data-stu-id="11edc-115">'T</span></span>

<span data-ttu-id="11edc-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="11edc-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="11edc-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="11edc-117">See Also</span></span>

- [<span data-ttu-id="11edc-118">Microsoft. Quantum. Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="11edc-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="11edc-119">Microsoft. Quantum. Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="11edc-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="11edc-120">Microsoft. Quantum. Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="11edc-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)