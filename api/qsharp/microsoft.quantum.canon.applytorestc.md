---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850489"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="cd61d-102">ApplyToRestC, operacja</span><span class="sxs-lookup"><span data-stu-id="cd61d-102">ApplyToRestC operation</span></span>

<span data-ttu-id="cd61d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cd61d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cd61d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd61d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd61d-105">Stosuje operację do wszystkich elementów oprócz pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="cd61d-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="cd61d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="cd61d-106">Description</span></span>

<span data-ttu-id="cd61d-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Rest(targets))` .</span><span class="sxs-lookup"><span data-stu-id="cd61d-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="cd61d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cd61d-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="cd61d-109">op: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="cd61d-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="cd61d-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="cd61d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="cd61d-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="cd61d-111">targets : 'T[]</span></span>

<span data-ttu-id="cd61d-112">Tablica elementów docelowych, z których wszystkie oprócz pierwszej zostaną zastosowane do `op` .</span><span class="sxs-lookup"><span data-stu-id="cd61d-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd61d-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd61d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cd61d-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="cd61d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cd61d-115">'C</span><span class="sxs-lookup"><span data-stu-id="cd61d-115">'T</span></span>

<span data-ttu-id="cd61d-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="cd61d-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd61d-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cd61d-117">See Also</span></span>

- [<span data-ttu-id="cd61d-118">Microsoft. Quantum. Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="cd61d-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="cd61d-119">Microsoft. Quantum. Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="cd61d-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="cd61d-120">Microsoft. Quantum. Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="cd61d-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)