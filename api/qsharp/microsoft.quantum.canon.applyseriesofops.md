---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841495"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="41676-102">ApplySeriesOfOps, operacja</span><span class="sxs-lookup"><span data-stu-id="41676-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="41676-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="41676-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="41676-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41676-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41676-105">Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy.</span><span class="sxs-lookup"><span data-stu-id="41676-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="41676-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="41676-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="41676-107">listOfOps: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="41676-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="41676-108">Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="41676-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="41676-109">Są one stosowane sekwencyjnie, najpierw najniższy indeks.</span><span class="sxs-lookup"><span data-stu-id="41676-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="41676-110">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="41676-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="41676-111">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="41676-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="41676-112">Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="41676-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="41676-113">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="41676-113">register : 'T[]</span></span>

<span data-ttu-id="41676-114">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="41676-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="41676-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="41676-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="41676-116">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="41676-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="41676-117">'C</span><span class="sxs-lookup"><span data-stu-id="41676-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="41676-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="41676-118">Example</span></span>

<span data-ttu-id="41676-119">Poniżej zawarto następujące zastosowania: EXP ([PauliX, PauliY], 0,5) do qubits 0, 1//then X do qubit 2 Let Ops = [EXP ([PauliX, PauliY], 0,5, _), ApplyToFirstQubit (X, _)]; Zezwól na indeksy = [[0, 1], [2]]; ApplySeriesOfOps (Ops, indeksy, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="41676-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="41676-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="41676-120">See Also</span></span>

- [<span data-ttu-id="41676-121">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="41676-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)