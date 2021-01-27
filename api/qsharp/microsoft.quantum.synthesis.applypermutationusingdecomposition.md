---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: ApplyPermutationUsingDecomposition, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 765b6d301363021f5b57a22f90e2ada38c9c09ec
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857391"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="5aa42-102">ApplyPermutationUsingDecomposition, operacja</span><span class="sxs-lookup"><span data-stu-id="5aa42-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="5aa42-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="5aa42-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="5aa42-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5aa42-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5aa42-105">Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="5aa42-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="5aa42-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5aa42-106">Description</span></span>

<span data-ttu-id="5aa42-107">Ta procedura implementuje podejście syntezy opartej na dekompozycji.</span><span class="sxs-lookup"><span data-stu-id="5aa42-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="5aa42-108">Dane wejściowe to Permutacja $ \pi $ przez $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, która reprezentuje $n $-Variable odwracalnej funkcji logicznej.</span><span class="sxs-lookup"><span data-stu-id="5aa42-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="5aa42-109">Algorytm iteracyjnie wykonuje następujące kroki dla każdego indeksu zmiennych $i $:</span><span class="sxs-lookup"><span data-stu-id="5aa42-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="5aa42-110">COMPUTE $ ((\ pi_l, \ pi_r), \pi ') $ w taki sposób, że obrazy $ \ pi_l $ i $ \ pi_r $ nie zmieniają bitów w ich elementach w indeksach innych niż $i $ i obrazy $ \pi ' $ nie zmieniają bitu $i $ w ich elementach.</span><span class="sxs-lookup"><span data-stu-id="5aa42-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="5aa42-111">Ustaw wartość $ \pi \leftarrow \pi "$" i Utwórz tabele prawdy z $ \ pi_l $ i $ \ pi_r $ na podstawie elementów, które nie są stałymi punktami.</span><span class="sxs-lookup"><span data-stu-id="5aa42-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="5aa42-112">Po zastosowaniu tych kroków dla wszystkich indeksów zmiennych, pozostała Permutacja $ \pi $ będzie tożsamość, a na podstawie zebranych tabel i indeksów prawdy można zastosować operacje kontrolowane w tabeli prawdy @"microsoft.quantum.intrinsic.x" przy użyciu @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operacji.</span><span class="sxs-lookup"><span data-stu-id="5aa42-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="5aa42-113">Zmienna Order to $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="5aa42-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="5aa42-114">W operacji można określić kolejność zmiennych niestandardowych @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="5aa42-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="5aa42-115">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5aa42-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="5aa42-116">uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5aa42-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5aa42-117">Permutacja elementów $2 ^ n $ zaczynających się od 0.</span><span class="sxs-lookup"><span data-stu-id="5aa42-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="5aa42-118">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5aa42-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5aa42-119">Lista $n $ qubits, do której zostanie zastosowana Permutacja.</span><span class="sxs-lookup"><span data-stu-id="5aa42-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5aa42-120">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5aa42-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="5aa42-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="5aa42-121">Example</span></span>

<span data-ttu-id="5aa42-122">Aby przeprowadzić syntezę `SWAP` operacji:</span><span class="sxs-lookup"><span data-stu-id="5aa42-122">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingDecomposition([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="5aa42-123">Odwołania</span><span class="sxs-lookup"><span data-stu-id="5aa42-123">References</span></span>

- [<span data-ttu-id="5aa42-124">*Alexis de Vos*, *Yvan van Rentergem*, ADV. in Math. of Communication. 2 (2), 2008, PP. 183--200</span><span class="sxs-lookup"><span data-stu-id="5aa42-124">*Alexis De Vos*, *Yvan Van Rentergem*, Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="5aa42-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, arkusz obliczeń symbolicznych 73 (2016), PP. 1--26</span><span class="sxs-lookup"><span data-stu-id="5aa42-125">*Mathias Soeken*, *Laura Tague*, *Gerhard W. Dueck*, *Rolf Drechsler*, Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="5aa42-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5aa42-126">See Also</span></span>

- [<span data-ttu-id="5aa42-127">Microsoft. Quantum. synteza. ApplyPermutationUsingDecompositionWithVariableOrder</span><span class="sxs-lookup"><span data-stu-id="5aa42-127">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="5aa42-128">Microsoft. Quantum. synteza. ApplyPermutationUsingTransformation</span><span class="sxs-lookup"><span data-stu-id="5aa42-128">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)