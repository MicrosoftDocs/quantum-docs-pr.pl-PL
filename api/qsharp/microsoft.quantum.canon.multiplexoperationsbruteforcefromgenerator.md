---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 395102c7ffffa81d1a9b6cbf29c9cc22fae6057e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852519"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="5bba2-102">MultiplexOperationsBruteForceFromGenerator, operacja</span><span class="sxs-lookup"><span data-stu-id="5bba2-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="5bba2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5bba2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5bba2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5bba2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5bba2-105">Stosuje przemnożoną przez siebie operację jednostkową $U $, która stosuje $V jednostkowe _j $, gdy jest to kontrolowane przez n-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="5bba2-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="5bba2-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="5bba2-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5bba2-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5bba2-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="5bba2-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 'r => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL)</span><span class="sxs-lookup"><span data-stu-id="5bba2-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="5bba2-109">Krotka, w której pierwszy element `Int` jest liczbą unitaries $N $, a drugi element `(Int -> ('T => () is Adj + Ctl))` to funkcja, która przyjmuje liczbę całkowitą $j $ w $ [0, N-1] $ i wyprowadza operację jednostkową $V _j $.</span><span class="sxs-lookup"><span data-stu-id="5bba2-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="5bba2-110">indeks: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5bba2-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5bba2-111">$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.</span><span class="sxs-lookup"><span data-stu-id="5bba2-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="5bba2-112">element docelowy: 'T</span><span class="sxs-lookup"><span data-stu-id="5bba2-112">target : 'T</span></span>

<span data-ttu-id="5bba2-113">Ogólny rejestr qubit, który $V _j $ działa.</span><span class="sxs-lookup"><span data-stu-id="5bba2-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5bba2-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5bba2-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5bba2-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5bba2-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5bba2-116">'C</span><span class="sxs-lookup"><span data-stu-id="5bba2-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="5bba2-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5bba2-117">Remarks</span></span>

<span data-ttu-id="5bba2-118">`coefficients` zostaną uzupełnione elementami tożsamości, jeśli określono mniej niż $2 ^ n $.</span><span class="sxs-lookup"><span data-stu-id="5bba2-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="5bba2-119">Ta wersja jest implementowana bezpośrednio przez zapętlenie przez operatorów opartych na podsystemie n.</span><span class="sxs-lookup"><span data-stu-id="5bba2-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>