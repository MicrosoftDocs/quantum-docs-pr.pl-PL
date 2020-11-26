---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 3c9ef9ade660e1f420d85162104d773b96722eeb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222613"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="6464c-102">MultiplyFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="6464c-102">MultiplyFxP operation</span></span>

<span data-ttu-id="6464c-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="6464c-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="6464c-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="6464c-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="6464c-105">Mnoży dwie liczby stałe w rejestrach Quantum.</span><span class="sxs-lookup"><span data-stu-id="6464c-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6464c-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6464c-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="6464c-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6464c-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6464c-108">Numer pierwszego ustalonego punktu.</span><span class="sxs-lookup"><span data-stu-id="6464c-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="6464c-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6464c-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6464c-110">Druga stała liczba punktów.</span><span class="sxs-lookup"><span data-stu-id="6464c-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="6464c-111">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="6464c-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="6464c-112">Liczba stałych punktów wyników musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="6464c-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6464c-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6464c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6464c-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="6464c-114">Remarks</span></span>

<span data-ttu-id="6464c-115">Bieżąca implementacja wymaga, aby trzy stałe numery miały tę samą pozycję punktu i taką samą liczbę qubits.</span><span class="sxs-lookup"><span data-stu-id="6464c-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>