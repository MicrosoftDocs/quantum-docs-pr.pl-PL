---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger
title: IncrementPhaseByModularInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: 52309c056a3eae25ffdfbfa848f94bf744c71132
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721056"
---
# <a name="incrementphasebymodularinteger-operation"></a><span data-ttu-id="e49cc-102">IncrementPhaseByModularInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="e49cc-102">IncrementPhaseByModularInteger operation</span></span>

<span data-ttu-id="e49cc-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="e49cc-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="e49cc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e49cc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e49cc-105">Wykonuje modularny przyrost qubit rejestru przez stałą całkowitą.</span><span class="sxs-lookup"><span data-stu-id="e49cc-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementPhaseByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="e49cc-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e49cc-106">Description</span></span>

<span data-ttu-id="e49cc-107">Poinformuj nas `increment` o $a $, `modulus` przez $N $ i Integer zakodowane w `target` $y $.</span><span class="sxs-lookup"><span data-stu-id="e49cc-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="e49cc-108">Następnie operacja wykonuje następujące przekształcenia: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} INTEGERS są zakodowane w formacie little-endian w QFT.</span><span class="sxs-lookup"><span data-stu-id="e49cc-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format in QFT basis.</span></span>

## <a name="input"></a><span data-ttu-id="e49cc-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e49cc-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="e49cc-110">Zwiększ: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e49cc-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e49cc-111">Przyrost liczby całkowitej $a $, który ma zostać dodany do $y $.</span><span class="sxs-lookup"><span data-stu-id="e49cc-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="e49cc-112">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e49cc-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e49cc-113">Liczba całkowita $N $, która modyfikacje $y + a $.</span><span class="sxs-lookup"><span data-stu-id="e49cc-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--phaselittleendian"></a><span data-ttu-id="e49cc-114">obiekt docelowy: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="e49cc-114">target : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="e49cc-115">Liczba całkowita $y $ w formacie little-endian z kodowaniem fazowym, `increment` do której dodano $a $.</span><span class="sxs-lookup"><span data-stu-id="e49cc-115">Integer $y$ in phase-encoded little-endian format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e49cc-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e49cc-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e49cc-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e49cc-117">Remarks</span></span>

<span data-ttu-id="e49cc-118">Zakłada, że `target` najwyższy bit ma ustawioną wartość 0.</span><span class="sxs-lookup"><span data-stu-id="e49cc-118">Assumes that `target` has the highest bit set to 0.</span></span>
<span data-ttu-id="e49cc-119">Zakłada również, że wartość docelowa jest mniejsza niż $N $.</span><span class="sxs-lookup"><span data-stu-id="e49cc-119">Also assumes that the value of target is less than $N$.</span></span>

<span data-ttu-id="e49cc-120">Aby zapoznać się ze schematem obwodu i wyjaśnieniem, zobacz rysunek 5 na [stronie 5 ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span><span class="sxs-lookup"><span data-stu-id="e49cc-120">For the circuit diagram and explanation see Figure 5 on [Page 5 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=5).</span></span>

## <a name="see-also"></a><span data-ttu-id="e49cc-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e49cc-121">See Also</span></span>

- [<span data-ttu-id="e49cc-122">Microsoft. Quantum. arytmetyczne. IncrementByModularInteger</span><span class="sxs-lookup"><span data-stu-id="e49cc-122">Microsoft.Quantum.Arithmetic.IncrementByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementByModularInteger)