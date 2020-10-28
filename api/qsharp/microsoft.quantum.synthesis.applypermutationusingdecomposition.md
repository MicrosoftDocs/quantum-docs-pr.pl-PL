---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725316"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="7dcd8-102">ApplyPermutationUsingDecomposition, operacja</span><span class="sxs-lookup"><span data-stu-id="7dcd8-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="7dcd8-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="7dcd8-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="7dcd8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7dcd8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7dcd8-105">Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="7dcd8-106">Opis</span><span class="sxs-lookup"><span data-stu-id="7dcd8-106">Description</span></span>

<span data-ttu-id="7dcd8-107">Ta procedura implementuje podejście syntezy opartej na dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="7dcd8-108">Dane wejściowe to Permutacja $ \pi $ przez $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, która reprezentuje $n $-Variable odwracalnej funkcji logicznej.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="7dcd8-109">Algorytm iteracyjnie wykonuje następujące kroki dla każdego indeksu zmiennych $i $:</span><span class="sxs-lookup"><span data-stu-id="7dcd8-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="7dcd8-110">COMPUTE $ ((\ pi_l, \ pi_r), \pi ') $ w taki sposób, że obrazy $ \ pi_l $ i $ \ pi_r $ nie zmieniają bitów w ich elementach w indeksach innych niż $i $ i obrazy $ \pi ' $ nie zmieniają bitu $i $ w ich elementach.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="7dcd8-111">Ustaw wartość $ \pi \leftarrow \pi "$" i Utwórz tabele prawdy z $ \ pi_l $ i $ \ pi_r $ na podstawie elementów, które nie są stałymi punktami.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="7dcd8-112">Po zastosowaniu tych kroków dla wszystkich indeksów zmiennych, pozostała Permutacja $ \pi $ będzie tożsamość, a na podstawie zebranych tabel i indeksów prawdy można zastosować operacje kontrolowane w tabeli prawdy @"microsoft.quantum.intrinsic.x" przy użyciu @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operacji.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="7dcd8-113">Zmienna Order to $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="7dcd8-114">W operacji można określić kolejność zmiennych niestandardowych @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="7dcd8-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="7dcd8-115">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7dcd8-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="7dcd8-116">uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7dcd8-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7dcd8-117">Permutacja elementów $2 ^ n $ zaczynających się od 0.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="7dcd8-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="7dcd8-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="7dcd8-119">Lista $n $ qubits, do której zostanie zastosowana Permutacja.</span><span class="sxs-lookup"><span data-stu-id="7dcd8-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7dcd8-120">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7dcd8-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="7dcd8-121">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="7dcd8-121">References</span></span>

- [<span data-ttu-id="7dcd8-122">*Alexis de Vos* , *Yvan van Rentergem* , ADV. in Math. of Communication. 2 (2), 2008, PP. 183--200</span><span class="sxs-lookup"><span data-stu-id="7dcd8-122">*Alexis De Vos* , *Yvan Van Rentergem* , Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="7dcd8-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , arkusz obliczeń symbolicznych 73 (2016), PP. 1--26</span><span class="sxs-lookup"><span data-stu-id="7dcd8-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="7dcd8-124">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7dcd8-124">See Also</span></span>

- [<span data-ttu-id="7dcd8-125">Microsoft. Quantum. synteza. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="7dcd8-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="7dcd8-126">Microsoft. Quantum. synteza. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="7dcd8-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)