---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717649"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="ca706-102">ApplySeriesOfOpsC, operacja</span><span class="sxs-lookup"><span data-stu-id="ca706-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="ca706-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca706-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca706-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca706-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca706-105">Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy.</span><span class="sxs-lookup"><span data-stu-id="ca706-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="ca706-106">Kontrolowane</span><span class="sxs-lookup"><span data-stu-id="ca706-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ca706-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ca706-107">Input</span></span>

### <a name="listofops--t--unit-ctl"></a><span data-ttu-id="ca706-108">listOfOps: t [] => CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="ca706-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="ca706-109">Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="ca706-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="ca706-110">Są one stosowane sekwencyjnie, najpierw najniższy indeks.</span><span class="sxs-lookup"><span data-stu-id="ca706-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="ca706-111">Każdy z nich musi mieć kontrolowany Funktor</span><span class="sxs-lookup"><span data-stu-id="ca706-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="ca706-112">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="ca706-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="ca706-113">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="ca706-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="ca706-114">Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="ca706-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="ca706-115">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="ca706-115">register : 'T[]</span></span>

<span data-ttu-id="ca706-116">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="ca706-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca706-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca706-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ca706-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="ca706-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca706-119">'C</span><span class="sxs-lookup"><span data-stu-id="ca706-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="ca706-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ca706-120">See Also</span></span>

- [<span data-ttu-id="ca706-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="ca706-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)