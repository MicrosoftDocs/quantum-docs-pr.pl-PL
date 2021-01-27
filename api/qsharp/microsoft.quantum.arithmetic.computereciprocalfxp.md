---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: db7425f1a8a9b5ddfdc6b123dad003298e3670e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843260"
---
# <a name="computereciprocalfxp-operation"></a><span data-ttu-id="a4ad0-102">ComputeReciprocalFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="a4ad0-102">ComputeReciprocalFxP operation</span></span>

<span data-ttu-id="a4ad0-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a4ad0-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a4ad0-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="a4ad0-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="a4ad0-105">Oblicza wartość $1/x $ dla ustalonej liczby $x $.</span><span class="sxs-lookup"><span data-stu-id="a4ad0-105">Computes $1/x$ for a fixed-point number $x$.</span></span>

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a4ad0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a4ad0-106">Input</span></span>

### <a name="x--fixedpoint"></a><span data-ttu-id="a4ad0-107">x: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a4ad0-107">x : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a4ad0-108">Liczba stałych punktów do odwrócenia.</span><span class="sxs-lookup"><span data-stu-id="a4ad0-108">Fixed-point number to be inverted.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="a4ad0-109">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a4ad0-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a4ad0-110">Liczba stałych punktów, która będzie przechowywać wynik.</span><span class="sxs-lookup"><span data-stu-id="a4ad0-110">Fixed-point number that will hold the result.</span></span> <span data-ttu-id="a4ad0-111">Musi być zainicjowany do $ \ket{0.0} $.</span><span class="sxs-lookup"><span data-stu-id="a4ad0-111">Must be initialized to $\ket{0.0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4ad0-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4ad0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

