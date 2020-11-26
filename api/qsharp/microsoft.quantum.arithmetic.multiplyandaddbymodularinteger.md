---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: MultiplyAndAddByModularInteger, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 169326879919b5b72d600c33d624776b720cc6bc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222596"
---
# <a name="multiplyandaddbymodularinteger-operation"></a><span data-ttu-id="32b02-102">MultiplyAndAddByModularInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="32b02-102">MultiplyAndAddByModularInteger operation</span></span>

<span data-ttu-id="32b02-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="32b02-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="32b02-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="32b02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="32b02-105">Wykonuje modułowe mnożenie i Dodawanie przez stałe wartości całkowite w rejestrze qubit.</span><span class="sxs-lookup"><span data-stu-id="32b02-105">Performs a modular multiply-and-add by integer constants on a qubit register.</span></span>

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="32b02-106">Opis</span><span class="sxs-lookup"><span data-stu-id="32b02-106">Description</span></span>

<span data-ttu-id="32b02-107">Implementuje mapę $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ dla danego modułu $N $, mnożnik stałych $a $ i summand $y $.</span><span class="sxs-lookup"><span data-stu-id="32b02-107">Implements the map $$ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $$ for a given modulus $N$, constant multiplier $a$, and summand $y$.</span></span>

## <a name="input"></a><span data-ttu-id="32b02-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="32b02-108">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="32b02-109">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32b02-109">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32b02-110">Liczba całkowita $a $ do dodania do każdej etykiety stanu podstawy.</span><span class="sxs-lookup"><span data-stu-id="32b02-110">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="32b02-111">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="32b02-111">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="32b02-112">Moduł $N $, który Dodawanie i mnożenie jest wykonywane w odniesieniu do.</span><span class="sxs-lookup"><span data-stu-id="32b02-112">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="32b02-113">mnożnik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="32b02-113">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="32b02-114">Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, którego wartość ma zostać dodana do każdej etykiety stanu podstawy `summand` .</span><span class="sxs-lookup"><span data-stu-id="32b02-114">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="summand--littleendian"></a><span data-ttu-id="32b02-115">summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="32b02-115">summand : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="32b02-116">Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, który ma być używany jako element docelowy dla tej operacji.</span><span class="sxs-lookup"><span data-stu-id="32b02-116">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="32b02-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="32b02-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="32b02-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="32b02-118">Remarks</span></span>

- <span data-ttu-id="32b02-119">Aby zapoznać się ze schematem obwodu i wyjaśnieniem, zobacz rysunek 6 na [stronie 7 z ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span><span class="sxs-lookup"><span data-stu-id="32b02-119">For the circuit diagram and explanation see Figure 6 on [Page 7 of arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)</span></span>
- <span data-ttu-id="32b02-120">Ta operacja odpowiada CMULT (a) MOD (N) w [ArXiv: Quant-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span><span class="sxs-lookup"><span data-stu-id="32b02-120">This operation corresponds to CMULT(a)MOD(N) in [arXiv:quant-ph/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)</span></span>

## <a name="see-also"></a><span data-ttu-id="32b02-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="32b02-121">See Also</span></span>

- [<span data-ttu-id="32b02-122">Microsoft. Quantum. arytmetyczne. MultiplyAndAddPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="32b02-122">Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)