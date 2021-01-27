---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844669"
---
# <a name="applyseriesofopsa-operation"></a><span data-ttu-id="a967e-102">ApplySeriesOfOpsA, operacja</span><span class="sxs-lookup"><span data-stu-id="a967e-102">ApplySeriesOfOpsA operation</span></span>

<span data-ttu-id="a967e-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a967e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a967e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a967e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a967e-105">Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy.</span><span class="sxs-lookup"><span data-stu-id="a967e-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="a967e-106">(Sąsiadujący)</span><span class="sxs-lookup"><span data-stu-id="a967e-106">(Adjoint)</span></span>

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="a967e-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a967e-107">Input</span></span>

### <a name="listofops--t--unit--is-adj"></a><span data-ttu-id="a967e-108">listOfOps: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą []</span><span class="sxs-lookup"><span data-stu-id="a967e-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="a967e-109">Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="a967e-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="a967e-110">Są one stosowane sekwencyjnie, najpierw najniższy indeks.</span><span class="sxs-lookup"><span data-stu-id="a967e-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="a967e-111">Każdy element musi mieć przyległych Funktor</span><span class="sxs-lookup"><span data-stu-id="a967e-111">Each must have an adjoint functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="a967e-112">elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="a967e-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="a967e-113">Zagnieżdżone tablice opisujące cele operacji.</span><span class="sxs-lookup"><span data-stu-id="a967e-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="a967e-114">Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.</span><span class="sxs-lookup"><span data-stu-id="a967e-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="a967e-115">Rejestr: t []</span><span class="sxs-lookup"><span data-stu-id="a967e-115">register : 'T[]</span></span>

<span data-ttu-id="a967e-116">Zarejestruj się, aby zarejestrować się w qubit.</span><span class="sxs-lookup"><span data-stu-id="a967e-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a967e-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a967e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a967e-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a967e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a967e-119">'C</span><span class="sxs-lookup"><span data-stu-id="a967e-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="a967e-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="a967e-120">Example</span></span>

<span data-ttu-id="a967e-121">Poniżej zawarto następujące zastosowania: EXP ([PauliX, PauliY], 0,5) do qubits 0, 1//then X do qubit 2 Let Ops = [EXP ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitA (X, _)]; Zezwól na indeksy = [[0, 1], [2]]; ApplySeriesOfOpsA (Ops, indeksy, qubitArray);</span><span class="sxs-lookup"><span data-stu-id="a967e-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitA(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsA(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="a967e-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a967e-122">See Also</span></span>

- [<span data-ttu-id="a967e-123">Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="a967e-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)