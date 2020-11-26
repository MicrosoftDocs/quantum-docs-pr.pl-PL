---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223395"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="d8e76-102">ComputeReciprocalFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="d8e76-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="d8e76-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d8e76-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d8e76-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="d8e76-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="d8e76-105">Oblicza wartość $1/x $ dla ustalonej liczby $x $.</span><span class="sxs-lookup"><span data-stu-id="d8e76-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d8e76-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d8e76-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="d8e76-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d8e76-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d8e76-108">Liczba stałych punktów do odwrócenia.</span><span class="sxs-lookup"><span data-stu-id="d8e76-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="d8e76-109">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="d8e76-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="d8e76-110">Liczba stałych punktów, która będzie przechowywać wynik.</span><span class="sxs-lookup"><span data-stu-id="d8e76-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="d8e76-111">Musi być zainicjowany do $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="d8e76-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8e76-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8e76-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

