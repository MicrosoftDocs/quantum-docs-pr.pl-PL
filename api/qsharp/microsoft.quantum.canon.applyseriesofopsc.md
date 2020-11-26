---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: eaa0ea3e33cce708af5879cfbe875397fbb82a8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217938"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="6b94f-102">ApplySeriesOfOpsC, operacja</span><span class="sxs-lookup"><span data-stu-id="6b94f-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="6b94f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b94f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b94f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b94f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b94f-105">Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy.</span><span class="sxs-lookup"><span data-stu-id="6b94f-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="6b94f-106">Kontrolowane</span><span class="sxs-lookup"><span data-stu-id="6b94f-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="6b94f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6b94f-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="6b94f-108">listOfOps: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL []</span><span class="sxs-lookup"><span data-stu-id="6b94f-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="6b94f-109">Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="6b94f-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="6b94f-110">Są one stosowane sekwencyjnie, najpierw najniższy indeks.</span><span class="sxs-lookup"><span data-stu-id="6b94f-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="6b94f-111">Każdy z nich musi mieć kontrolowany Funktor</span><span class="sxs-lookup"><span data-stu-id="6b94f-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="6b94f-112">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="6b94f-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="6b94f-113">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="6b94f-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="6b94f-114">Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="6b94f-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="6b94f-115">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="6b94f-115">register : 'T[]</span></span>

<span data-ttu-id="6b94f-116">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="6b94f-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b94f-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b94f-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b94f-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="6b94f-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b94f-119">'C</span><span class="sxs-lookup"><span data-stu-id="6b94f-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="6b94f-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b94f-120">See Also</span></span>

- [<span data-ttu-id="6b94f-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="6b94f-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)