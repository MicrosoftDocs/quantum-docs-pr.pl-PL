---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 2fde0bf391568f39128e6dca4b535aa6b78407c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715801"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="b039a-102">MultiplexOperationsFromGenerator, operacja</span><span class="sxs-lookup"><span data-stu-id="b039a-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="b039a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b039a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b039a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b039a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b039a-105">Stosuje przemnożoną przez siebie operację jednostkową $U $, która stosuje $V jednostkowe _j $, gdy jest to kontrolowane przez n-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="b039a-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="b039a-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="b039a-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="b039a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b039a-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit-adj--ctl"></a><span data-ttu-id="b039a-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => b: korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL)</span><span class="sxs-lookup"><span data-stu-id="b039a-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="b039a-109">Krotka, w której pierwszy element `Int` jest liczbą unitaries $N $, a drugi element `(Int -> ('T => () is Adj + Ctl))` to funkcja, która przyjmuje liczbę całkowitą $j $ w $ [0, N-1] $ i wyprowadza operację jednostkową $V _j $.</span><span class="sxs-lookup"><span data-stu-id="b039a-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="b039a-110">indeks: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="b039a-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="b039a-111">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="b039a-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="b039a-112">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="b039a-112">target : 'T</span></span>

<span data-ttu-id="b039a-113">Ogólny rejestr qubit, który $V _j $ działa.</span><span class="sxs-lookup"><span data-stu-id="b039a-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b039a-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b039a-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b039a-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b039a-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b039a-116">'C</span><span class="sxs-lookup"><span data-stu-id="b039a-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b039a-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b039a-117">Remarks</span></span>

<span data-ttu-id="b039a-118">`coefficients` zostaną uzupełnione elementami tożsamości, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="b039a-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="b039a-119">Ta implementacja używa qubits pomocniczego $n-$1.</span><span class="sxs-lookup"><span data-stu-id="b039a-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="b039a-120">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="b039a-120">References</span></span>

- [<span data-ttu-id="b039a-121">*Andrew M. Childs, Dmitri Maslov, Yunseong, Neila J. Ross, Juan Su* , ArXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="b039a-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su* , arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)