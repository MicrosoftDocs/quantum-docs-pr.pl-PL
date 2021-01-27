---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 776ccb7a9e1ba1a34b28da6e1cf3a0aafe9da76b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843049"
---
# <a name="multiplyfxp-operation"></a><span data-ttu-id="f22d3-102">MultiplyFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="f22d3-102">MultiplyFxP operation</span></span>

<span data-ttu-id="f22d3-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f22d3-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f22d3-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f22d3-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f22d3-105">Mnoży dwie liczby stałe w rejestrach Quantum.</span><span class="sxs-lookup"><span data-stu-id="f22d3-105">Multiplies two fixed-point numbers in quantum registers.</span></span>

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f22d3-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f22d3-106">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="f22d3-107">FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f22d3-107">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f22d3-108">Numer pierwszego ustalonego punktu.</span><span class="sxs-lookup"><span data-stu-id="f22d3-108">First fixed-point number.</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="f22d3-109">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f22d3-109">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f22d3-110">Druga stała liczba punktów.</span><span class="sxs-lookup"><span data-stu-id="f22d3-110">Second fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="f22d3-111">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f22d3-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f22d3-112">Liczba stałych punktów wyników musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="f22d3-112">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f22d3-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f22d3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f22d3-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f22d3-114">Remarks</span></span>

<span data-ttu-id="f22d3-115">Bieżąca implementacja wymaga, aby trzy stałe numery miały tę samą pozycję punktu i taką samą liczbę qubits.</span><span class="sxs-lookup"><span data-stu-id="f22d3-115">The current implementation requires the three fixed-point numbers to have the same point position and the same number of qubits.</span></span>