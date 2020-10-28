---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717234"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="72adc-102">ApplyToHeadCA, operacja</span><span class="sxs-lookup"><span data-stu-id="72adc-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="72adc-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="72adc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="72adc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72adc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="72adc-105">Stosuje operację do pierwszego elementu tablicy.</span><span class="sxs-lookup"><span data-stu-id="72adc-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="72adc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="72adc-106">Description</span></span>

<span data-ttu-id="72adc-107">`op`Ma zastosowanie operacja i Tablica elementów docelowych `targets` `op(Head(targets))` .</span><span class="sxs-lookup"><span data-stu-id="72adc-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="72adc-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="72adc-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="72adc-109">op: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="72adc-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="72adc-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="72adc-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="72adc-111">elementy docelowe: t []</span><span class="sxs-lookup"><span data-stu-id="72adc-111">targets : 'T[]</span></span>

<span data-ttu-id="72adc-112">Tablica elementów docelowych, do których zostanie zastosowany pierwszy `op` .</span><span class="sxs-lookup"><span data-stu-id="72adc-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72adc-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72adc-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72adc-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="72adc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72adc-115">'C</span><span class="sxs-lookup"><span data-stu-id="72adc-115">'T</span></span>

<span data-ttu-id="72adc-116">Typ wejściowy operacji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="72adc-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="72adc-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="72adc-117">See Also</span></span>

- [<span data-ttu-id="72adc-118">Microsoft. Quantum. Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="72adc-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="72adc-119">Microsoft. Quantum. Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="72adc-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="72adc-120">Microsoft. Quantum. Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="72adc-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)