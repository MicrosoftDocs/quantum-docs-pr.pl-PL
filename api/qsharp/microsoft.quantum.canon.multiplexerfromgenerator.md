---
uid: Microsoft.Quantum.Canon.MultiplexerFromGenerator
title: MultiplexerFromGenerator, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexerFromGenerator
qsharp.summary: >-
  Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 327d995d3870732887f880778eb289c3aad1f030
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715890"
---
# <a name="multiplexerfromgenerator-function"></a><span data-ttu-id="ecb61-102">MultiplexerFromGenerator, funkcja</span><span class="sxs-lookup"><span data-stu-id="ecb61-102">MultiplexerFromGenerator function</span></span>

<span data-ttu-id="ecb61-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ecb61-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ecb61-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ecb61-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ecb61-105">Zwraca przemnożoną operację jednostkową $U $, która stosuje $V jednostkowe _j $, gdy jest to kontrolowane przez n-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="ecb61-105">Returns a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="ecb61-106">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="ecb61-106">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
function MultiplexerFromGenerator (unitaryGenerator : (Int, (Int -> (Qubit[] => Unit is Adj + Ctl)))) : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="ecb61-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ecb61-107">Input</span></span>

### <a name="unitarygenerator--intint---qubit--unit-adj--ctl"></a><span data-ttu-id="ecb61-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL)</span><span class="sxs-lookup"><span data-stu-id="ecb61-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

<span data-ttu-id="ecb61-109">Krotka, w której pierwszy element `Int` jest liczbą unitaries $N $, a drugi element `(Int -> ('T => () is Adj + Ctl))` to funkcja, która przyjmuje liczbę całkowitą $j $ w $ [0, N-1] $ i wyprowadza operację jednostkową $V _j $.</span><span class="sxs-lookup"><span data-stu-id="ecb61-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>



## <a name="output--littleendianqubit--unit-adj--ctl"></a><span data-ttu-id="ecb61-110">Output: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="ecb61-110">Output : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="ecb61-111">Przemnożona przez siebie operacja jednostkowa $U $, która stosuje unitaries opisane przez `unitaryGenerator` .</span><span class="sxs-lookup"><span data-stu-id="ecb61-111">A multiply-controlled unitary operation $U$ that applies unitaries described by `unitaryGenerator`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecb61-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ecb61-112">See Also</span></span>

- [<span data-ttu-id="ecb61-113">Microsoft. Quantum. Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="ecb61-113">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)