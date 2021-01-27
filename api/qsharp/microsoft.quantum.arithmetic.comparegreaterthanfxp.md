---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: f49c713c8a1e8a6451f2c54fa59a72f00bfbb4c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843321"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="8c8ee-102">CompareGreaterThanFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="8c8ee-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="8c8ee-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="8c8ee-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="8c8ee-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="8c8ee-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="8c8ee-105">Porównuje dwie stałe numery przechowywane w rejestrach Quantum i kontroluje odbicie w wyniku.</span><span class="sxs-lookup"><span data-stu-id="8c8ee-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8c8ee-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8c8ee-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="8c8ee-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8c8ee-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8c8ee-108">Pierwsza stała liczba do porównania.</span><span class="sxs-lookup"><span data-stu-id="8c8ee-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="8c8ee-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="8c8ee-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="8c8ee-110">Druga liczba stałych punktów do porównania.</span><span class="sxs-lookup"><span data-stu-id="8c8ee-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="8c8ee-111">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8c8ee-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8c8ee-112">Wynik porównania.</span><span class="sxs-lookup"><span data-stu-id="8c8ee-112">Result of the comparison.</span></span> <span data-ttu-id="8c8ee-113">Zostanie odwrócony, jeśli `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="8c8ee-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8c8ee-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8c8ee-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="8c8ee-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="8c8ee-115">Remarks</span></span>

<span data-ttu-id="8c8ee-116">Bieżąca implementacja wymaga, aby dwie stałe numery miały tę samą pozycję punktu i taką samą liczbę qubits.</span><span class="sxs-lookup"><span data-stu-id="8c8ee-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>