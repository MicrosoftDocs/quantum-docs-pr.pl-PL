---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: f33d2980ff1775b1ae8d2e2e7a4fa1e5cbe7d5ba
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858879"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="aacd4-102">ApplyPermutationUsingDecompositionWithVariableOrder, operacja</span><span class="sxs-lookup"><span data-stu-id="aacd4-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="aacd4-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="aacd4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="aacd4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aacd4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aacd4-105">Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="aacd4-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="aacd4-106">Opis</span><span class="sxs-lookup"><span data-stu-id="aacd4-106">Description</span></span>

<span data-ttu-id="aacd4-107">Ta operacja jest bardziej ogólną wersją, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" w której można określić kolejność zmiennych.</span><span class="sxs-lookup"><span data-stu-id="aacd4-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="aacd4-108">Inna kolejność zmiennych zmienia sekwencję dekompozycji i tabele prawdy używane dla bram sterowanych @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="aacd4-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="aacd4-109">W związku z tym zmiana kolejności zmiennych zmienia liczbę ogólnych bram używanych do realizacji permutacji.</span><span class="sxs-lookup"><span data-stu-id="aacd4-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="aacd4-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aacd4-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="aacd4-111">uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aacd4-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aacd4-112">Permutacja elementów $2 ^ n $ zaczynających się od 0.</span><span class="sxs-lookup"><span data-stu-id="aacd4-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="aacd4-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="aacd4-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="aacd4-114">Permutacja $n $ elementów rozpoczynając od 0.</span><span class="sxs-lookup"><span data-stu-id="aacd4-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="aacd4-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="aacd4-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="aacd4-116">Lista $n $ qubits, do której zostanie zastosowana Permutacja.</span><span class="sxs-lookup"><span data-stu-id="aacd4-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aacd4-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aacd4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="aacd4-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="aacd4-118">Example</span></span>

<span data-ttu-id="aacd4-119">Aby przeprowadzić syntezę `SWAP` operacji:</span><span class="sxs-lookup"><span data-stu-id="aacd4-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecompositionWithVariableOrder([0, 2, 1, 3], [1, 0], LittleEndian(qubits));
}
```

## <a name="see-also"></a><span data-ttu-id="aacd4-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aacd4-120">See Also</span></span>

- [<span data-ttu-id="aacd4-121">Microsoft. Quantum. synteza. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="aacd4-121">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="aacd4-122">Microsoft. Quantum. synteza. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="aacd4-122">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)