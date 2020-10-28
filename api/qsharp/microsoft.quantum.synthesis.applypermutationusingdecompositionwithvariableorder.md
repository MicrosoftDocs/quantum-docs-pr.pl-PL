---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder
title: ApplyPermutationUsingDecompositionWithVariableOrder, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecompositionWithVariableOrder
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 1edbc0a2948fdf3ae67f14b3c552676feaa7f498
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725297"
---
# <a name="applypermutationusingdecompositionwithvariableorder-operation"></a><span data-ttu-id="16326-102">ApplyPermutationUsingDecompositionWithVariableOrder, operacja</span><span class="sxs-lookup"><span data-stu-id="16326-102">ApplyPermutationUsingDecompositionWithVariableOrder operation</span></span>

<span data-ttu-id="16326-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="16326-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="16326-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16326-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16326-105">Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="16326-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecompositionWithVariableOrder (perm : Int[], variableOrder : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="16326-106">Opis</span><span class="sxs-lookup"><span data-stu-id="16326-106">Description</span></span>

<span data-ttu-id="16326-107">Ta operacja jest bardziej ogólną wersją, @"microsoft.quantum.synthesis.applypermutationusingdecomposition" w której można określić kolejność zmiennych.</span><span class="sxs-lookup"><span data-stu-id="16326-107">This operation is a more general version of @"microsoft.quantum.synthesis.applypermutationusingdecomposition" in which the variable order can be specified.</span></span> <span data-ttu-id="16326-108">Inna kolejność zmiennych zmienia sekwencję dekompozycji i tabele prawdy używane dla bram sterowanych @"microsoft.quantum.intrinsic.x" .</span><span class="sxs-lookup"><span data-stu-id="16326-108">A different variable order changes the decomposition sequence and the truth tables used for the controlled @"microsoft.quantum.intrinsic.x" gates.</span></span>  <span data-ttu-id="16326-109">W związku z tym zmiana kolejności zmiennych zmienia liczbę ogólnych bram używanych do realizacji permutacji.</span><span class="sxs-lookup"><span data-stu-id="16326-109">Therefore, changing the variable order changes the number of overall gates used to realize the permutation.</span></span>

## <a name="input"></a><span data-ttu-id="16326-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="16326-110">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="16326-111">uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="16326-111">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="16326-112">Permutacja elementów $2 ^ n $ zaczynających się od 0.</span><span class="sxs-lookup"><span data-stu-id="16326-112">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="variableorder--int"></a><span data-ttu-id="16326-113">variableOrder: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="16326-113">variableOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="16326-114">Permutacja $n $ elementów rozpoczynając od 0.</span><span class="sxs-lookup"><span data-stu-id="16326-114">A permutation of $n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="16326-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="16326-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="16326-116">Lista $n $ qubits, do której zostanie zastosowana Permutacja.</span><span class="sxs-lookup"><span data-stu-id="16326-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16326-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16326-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="16326-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="16326-118">See Also</span></span>

- [<span data-ttu-id="16326-119">Microsoft. Quantum. synteza. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="16326-119">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)
- [<span data-ttu-id="16326-120">Microsoft. Quantum. synteza. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="16326-120">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)