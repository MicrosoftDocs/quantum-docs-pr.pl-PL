---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717654"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="08de6-102">ApplySeriesOfOpsA, operacja</span><span class="sxs-lookup"><span data-stu-id="08de6-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="08de6-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="08de6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="08de6-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08de6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08de6-105">Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy.</span><span class="sxs-lookup"><span data-stu-id="08de6-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="08de6-106">(Sąsiadujący)</span><span class="sxs-lookup"><span data-stu-id="08de6-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="08de6-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="08de6-107">Input</span></span>

### <a name="listofops--t--unit-adj"></a><span data-ttu-id="08de6-108">listOfOps: t [] => korektę [jednostki](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="08de6-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="08de6-109">Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="08de6-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="08de6-110">Są one stosowane sekwencyjnie, najpierw najniższy indeks.</span><span class="sxs-lookup"><span data-stu-id="08de6-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="08de6-111">Każdy element musi mieć przyległych Funktor</span><span class="sxs-lookup"><span data-stu-id="08de6-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="08de6-112">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="08de6-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="08de6-113">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="08de6-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="08de6-114">Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="08de6-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="08de6-115">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="08de6-115">register : 'T[]</span></span>

<span data-ttu-id="08de6-116">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="08de6-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="08de6-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="08de6-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="08de6-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="08de6-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="08de6-119">'C</span><span class="sxs-lookup"><span data-stu-id="08de6-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="08de6-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="08de6-120">See Also</span></span>

- [<span data-ttu-id="08de6-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="08de6-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)