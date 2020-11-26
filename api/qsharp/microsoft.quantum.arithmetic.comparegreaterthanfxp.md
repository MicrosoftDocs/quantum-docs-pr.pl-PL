---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: 1e9afc7645f62b932fa8ebc3d33e21a2a5182361
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223531"
---
# <a name="comparegreaterthanfxp-operation"></a><span data-ttu-id="d927f-102">CompareGreaterThanFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="d927f-102">CompareGreaterThanFxP operation</span></span>

<span data-ttu-id="d927f-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d927f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d927f-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d927f-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d927f-105">Porównuje dwie stałe numery przechowywane w rejestrach Quantum i kontroluje odbicie w wyniku.</span><span class="sxs-lookup"><span data-stu-id="d927f-105">Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.</span></span>

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d927f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d927f-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="d927f-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d927f-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d927f-108">Pierwsza stała liczba do porównania.</span><span class="sxs-lookup"><span data-stu-id="d927f-108">First fixed-point number to be compared.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="d927f-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d927f-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d927f-110">Druga liczba stałych punktów do porównania.</span><span class="sxs-lookup"><span data-stu-id="d927f-110">Second fixed-point number to be compared.</span></span>


### <a name="result--qubit"></a><span data-ttu-id="d927f-111">wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="d927f-111">result : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="d927f-112">Wynik porównania.</span><span class="sxs-lookup"><span data-stu-id="d927f-112">Result of the comparison.</span></span> <span data-ttu-id="d927f-113">Zostanie odwrócony, jeśli `fp1 > fp2` .</span><span class="sxs-lookup"><span data-stu-id="d927f-113">Will be flipped if `fp1 > fp2`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d927f-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d927f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d927f-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d927f-115">Remarks</span></span>

<span data-ttu-id="d927f-116">Bieżąca implementacja wymaga, aby dwie stałe numery miały tę samą pozycję punktu i taką samą liczbę qubits.</span><span class="sxs-lookup"><span data-stu-id="d927f-116">The current implementation requires the two fixed-point numbers to have the same point position and the same number of qubits.</span></span>