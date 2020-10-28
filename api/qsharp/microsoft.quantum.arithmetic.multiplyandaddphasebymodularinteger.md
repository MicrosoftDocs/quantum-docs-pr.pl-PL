---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719805"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a><span data-ttu-id="39dd1-102">MultiplyAndAddPhaseByModularInteger, operacja</span><span class="sxs-lookup"><span data-stu-id="39dd1-102">MultiplyAndAddPhaseByModularInteger operation</span></span>

<span data-ttu-id="39dd1-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="39dd1-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="39dd1-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="39dd1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="39dd1-105">Taka sama jak MultiplyAndAddByModularInteger, ale zakłada, że summand koduje liczby całkowite na bazie QFT.</span><span class="sxs-lookup"><span data-stu-id="39dd1-105">The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.</span></span>

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="39dd1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="39dd1-106">Input</span></span>

### <a name="constmultiplier--int"></a><span data-ttu-id="39dd1-107">constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39dd1-107">constMultiplier : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39dd1-108">Liczba całkowita $a $ do dodania do każdej etykiety stanu podstawy.</span><span class="sxs-lookup"><span data-stu-id="39dd1-108">An integer $a$ to be added to each basis state label.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="39dd1-109">Moduł: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39dd1-109">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39dd1-110">Moduł $N $, który Dodawanie i mnożenie jest wykonywane w odniesieniu do.</span><span class="sxs-lookup"><span data-stu-id="39dd1-110">The modulus $N$ which addition and multiplication is taken with respect to.</span></span>


### <a name="multiplier--littleendian"></a><span data-ttu-id="39dd1-111">mnożnik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="39dd1-111">multiplier : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="39dd1-112">Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, którego wartość ma zostać dodana do każdej etykiety stanu podstawy `summand` .</span><span class="sxs-lookup"><span data-stu-id="39dd1-112">A quantum register representing an unsigned integer whose value is to be added to each basis state label of `summand`.</span></span>


### <a name="phasesummand--phaselittleendian"></a><span data-ttu-id="39dd1-113">phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span><span class="sxs-lookup"><span data-stu-id="39dd1-113">phaseSummand : [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)</span></span>

<span data-ttu-id="39dd1-114">Rejestr Quantum reprezentujący liczbę całkowitą bez znaku, który ma być używany jako element docelowy dla tej operacji.</span><span class="sxs-lookup"><span data-stu-id="39dd1-114">A quantum register representing an unsigned integer to use as the target for this operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="39dd1-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39dd1-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="39dd1-116">Uwagi</span><span class="sxs-lookup"><span data-stu-id="39dd1-116">Remarks</span></span>

<span data-ttu-id="39dd1-117">Zakłada, że `phaseSummand` najwyższy bit ma ustawioną wartość 0.</span><span class="sxs-lookup"><span data-stu-id="39dd1-117">Assumes that `phaseSummand` has the highest bit set to 0.</span></span>
<span data-ttu-id="39dd1-118">Zakłada również, że wartość `phaseSummand` jest mniejsza niż $N $.</span><span class="sxs-lookup"><span data-stu-id="39dd1-118">Also assumes that the value of `phaseSummand` is less than $N$.</span></span>

## <a name="see-also"></a><span data-ttu-id="39dd1-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="39dd1-119">See Also</span></span>

- [<span data-ttu-id="39dd1-120">Microsoft. Quantum. arytmetyczne. MultiplyAndAddByModularInteger</span><span class="sxs-lookup"><span data-stu-id="39dd1-120">Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)