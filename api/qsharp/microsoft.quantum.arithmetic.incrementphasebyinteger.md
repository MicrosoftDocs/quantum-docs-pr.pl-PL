---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 54b83b3d4460c05478543c51f8f9c0b0e7f5b1fa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222919"
---
# <a name="incrementphasebyinteger-operation"></a><span data-ttu-id="568e5-102">IncrementPhaseByInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="568e5-102">IncrementPhaseByInteger operation</span></span>

<span data-ttu-id="568e5-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="568e5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="568e5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="568e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="568e5-105">Zwiększa niepodpisany rejestr Quantum przez klasyczną liczbę całkowitą, używając rotacji faz.</span><span class="sxs-lookup"><span data-stu-id="568e5-105">Increments an unsigned quantum register by a classical integer, using phase rotations.</span></span>

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="568e5-106">Opis</span><span class="sxs-lookup"><span data-stu-id="568e5-106">Description</span></span>

<span data-ttu-id="568e5-107">Załóżmy, że `target` koduje liczbę całkowitą bez znaku $x $ w kodowaniu little-endian i która `increment` jest równa $a $.</span><span class="sxs-lookup"><span data-stu-id="568e5-107">Suppose that `target` encodes an unsigned integer $x$ in a little-endian encoding and that `increment` is equal to $a$.</span></span>
<span data-ttu-id="568e5-108">Następnie ta operacja implementuje moduł $ \ket{x} \mapsto \ket{x + a} $, w którym jest wykonywane dzielenie modulo $2 ^ n $, gdzie $n = \texttt{Length (target!)} $.</span><span class="sxs-lookup"><span data-stu-id="568e5-108">Then, this operation implements the unitary $\ket{x} \mapsto \ket{x + a}$, where the addition is performed modulo $2^n$, where $n = \texttt{Length(target!)}$.</span></span>

## <a name="input"></a><span data-ttu-id="568e5-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="568e5-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="568e5-110">Zwiększ: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="568e5-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="568e5-111">Liczba całkowita, przez którą `target` jest zwiększana wartość.</span><span class="sxs-lookup"><span data-stu-id="568e5-111">The integer by which the `target` is incremented by.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="568e5-112">obiekt docelowy: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="568e5-112">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="568e5-113">Rejestr Quantum zarejestruje liczbę całkowitą bez znaku przy użyciu kodowania little-endian na zasadzie podwójnej (QFT).</span><span class="sxs-lookup"><span data-stu-id="568e5-113">A quantum register encoding an unsigned integer using little-endian encoding in the dual (QFT) basis.</span></span>



## <a name="output--unit"></a><span data-ttu-id="568e5-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="568e5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="568e5-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="568e5-115">Remarks</span></span>

<span data-ttu-id="568e5-116">Należy pamiętać, że uproszczono obwód, ponieważ przyrost jest klasyczną stałą, a nie rejestrem Quantum.</span><span class="sxs-lookup"><span data-stu-id="568e5-116">Note that we have simplified the circuit because the increment is a classical constant, not a quantum register.</span></span>

<span data-ttu-id="568e5-117">Zobacz rysunek na [ stronie 6 of ArXiv: Quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) dla diagramu obwodu i wyjaśnienie.</span><span class="sxs-lookup"><span data-stu-id="568e5-117">See the figure on [ Page 6 of arXiv:quant-ph/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) for the circuit diagram and explanation.</span></span>

## <a name="references"></a><span data-ttu-id="568e5-118">Odwołania</span><span class="sxs-lookup"><span data-stu-id="568e5-118">References</span></span>

- [<span data-ttu-id="568e5-119">*Thomas G. Draper*, ArXiv: Quant-pH/0008033</span><span class="sxs-lookup"><span data-stu-id="568e5-119"> *Thomas G. Draper*, arXiv:quant-ph/0008033</span></span>](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a><span data-ttu-id="568e5-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="568e5-120">See Also</span></span>

- [<span data-ttu-id="568e5-121">Microsoft. Quantum. arytmetyczne. IncrementByInteger</span><span class="sxs-lookup"><span data-stu-id="568e5-121">Microsoft.Quantum.Arithmetic.IncrementByInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)