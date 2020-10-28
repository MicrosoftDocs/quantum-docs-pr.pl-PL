---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721248"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="80102-102">ComputeReciprocalFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="80102-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="80102-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="80102-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="80102-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="80102-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="80102-105">Oblicza wartość $1/x $ dla ustalonej liczby $x $.</span><span class="sxs-lookup"><span data-stu-id="80102-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="80102-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="80102-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="80102-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="80102-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="80102-108">Liczba stałych punktów do odwrócenia.</span><span class="sxs-lookup"><span data-stu-id="80102-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="80102-109">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="80102-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="80102-110">Liczba stałych punktów, która będzie przechowywać wynik.</span><span class="sxs-lookup"><span data-stu-id="80102-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="80102-111">Musi być zainicjowany do $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="80102-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="80102-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80102-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

