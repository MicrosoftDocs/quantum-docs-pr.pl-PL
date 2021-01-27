---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation
title: ApplyPermutationUsingTransformation, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingTransformation
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.
ms.openlocfilehash: 79913bec44514d477b7ee0668b43396b297b9ab8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858995"
---
# <a name="applypermutationusingtransformation-operation"></a><span data-ttu-id="885de-102">ApplyPermutationUsingTransformation, operacja</span><span class="sxs-lookup"><span data-stu-id="885de-102">ApplyPermutationUsingTransformation operation</span></span>

<span data-ttu-id="885de-103">Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="885de-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="885de-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="885de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="885de-105">Permutes amplitud w stanie Quantum przy użyciu syntezy opartej na transformacji.</span><span class="sxs-lookup"><span data-stu-id="885de-105">Permutes the amplitudes in a quantum state given a permutation using transformation-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingTransformation (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="885de-106">Opis</span><span class="sxs-lookup"><span data-stu-id="885de-106">Description</span></span>

<span data-ttu-id="885de-107">Ta procedura implementuje jednokierunkowe podejście syntezy opartej na transformacji.</span><span class="sxs-lookup"><span data-stu-id="885de-107">This procedure implements the unidirectional transformation based synthesis approach.</span></span>  <span data-ttu-id="885de-108">Dane wejściowe to Permutacja $ \pi $ przez $2 ^ n $ elementy $ \{ 0, \dots, 2 ^ n-1 \} $, która reprezentuje $n $-Variable odwracalnej funkcji logicznej.</span><span class="sxs-lookup"><span data-stu-id="885de-108">Input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="885de-109">Algorytm wykonuje iteracyjnie następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="885de-109">The algorithm performs iteratively the following steps:</span></span>

1. <span data-ttu-id="885de-110">Znajdź najmniejszy $x $ taki, który $x \ne \pi (x) = y $.</span><span class="sxs-lookup"><span data-stu-id="885de-110">Find smallest $x$ such that $x \ne \pi(x) = y$.</span></span>
2. <span data-ttu-id="885de-111">Znajdź wielokontrolowane operacje Toffoli, które mają zastosowanie do danych wyjściowych $ \pi (x) = x $ i nie zmieniaj $ \pi (x ') $ dla wszystkich $x "< x $</span><span class="sxs-lookup"><span data-stu-id="885de-111">Find multiple-controlled Toffoli operations, which applied to the outputs make $\pi(x) = x$ and do not change $\pi(x')$ for all $x' < x$</span></span>

## <a name="input"></a><span data-ttu-id="885de-112">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="885de-112">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="885de-113">uprawnienie: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="885de-113">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="885de-114">Permutacja elementów $2 ^ n $ zaczynających się od 0.</span><span class="sxs-lookup"><span data-stu-id="885de-114">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="885de-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="885de-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="885de-116">Lista $n $ qubits, do której zostanie zastosowana Permutacja.</span><span class="sxs-lookup"><span data-stu-id="885de-116">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="885de-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="885de-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="885de-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="885de-118">Example</span></span>

<span data-ttu-id="885de-119">Aby przeprowadzić syntezę `SWAP` operacji:</span><span class="sxs-lookup"><span data-stu-id="885de-119">To synthesize a `SWAP` operation:</span></span>

```qsharp
using (qubits = Qubit[2]) {
  ApplyPermutationUsingTransformation([0, 2, 1, 3], LittleEndian(qubits));
}
```

## <a name="references"></a><span data-ttu-id="885de-120">Odwołania</span><span class="sxs-lookup"><span data-stu-id="885de-120">References</span></span>

- [<span data-ttu-id="885de-121">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, proc. DAC 2003, IEEE, PP. 318-323, 2003</span><span class="sxs-lookup"><span data-stu-id="885de-121">*D. Michael Miller*, *Dmitri Maslov*, *Gerhard W. Dueck*, Proc. DAC 2003, IEEE, pp. 318-323, 2003</span></span>](https://doi.org/10.1145/775832.775915)
- [<span data-ttu-id="885de-122">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, proc. RC 2016, Springer, PP. 307-321, 2016</span><span class="sxs-lookup"><span data-stu-id="885de-122">*Mathias Soeken*, *Gerhard W. Dueck*, *D. Michael Miller*, Proc. RC 2016, Springer, pp. 307-321, 2016</span></span>](https://doi.org/10.1007/978-3-319-40578-0_22)

## <a name="see-also"></a><span data-ttu-id="885de-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="885de-123">See Also</span></span>

- [<span data-ttu-id="885de-124">Microsoft. Quantum. synteza. ApplyPermutationUsingDecomposition</span><span class="sxs-lookup"><span data-stu-id="885de-124">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition)