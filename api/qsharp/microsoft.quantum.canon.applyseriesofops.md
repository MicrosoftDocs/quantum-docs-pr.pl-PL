---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717668"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="92d9d-102">ApplySeriesOfOps, operacja</span><span class="sxs-lookup"><span data-stu-id="92d9d-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="92d9d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="92d9d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="92d9d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92d9d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92d9d-105">Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy.</span><span class="sxs-lookup"><span data-stu-id="92d9d-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="92d9d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="92d9d-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="92d9d-107">listOfOps: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="92d9d-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="92d9d-108">Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="92d9d-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="92d9d-109">Są one stosowane sekwencyjnie, najpierw najniższy indeks.</span><span class="sxs-lookup"><span data-stu-id="92d9d-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="92d9d-110">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="92d9d-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="92d9d-111">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="92d9d-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="92d9d-112">Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="92d9d-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="92d9d-113">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="92d9d-113">register : 'T[]</span></span>

<span data-ttu-id="92d9d-114">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="92d9d-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="92d9d-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="92d9d-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="92d9d-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="92d9d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="92d9d-117">'C</span><span class="sxs-lookup"><span data-stu-id="92d9d-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="92d9d-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="92d9d-118">See Also</span></span>

- [<span data-ttu-id="92d9d-119">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="92d9d-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)