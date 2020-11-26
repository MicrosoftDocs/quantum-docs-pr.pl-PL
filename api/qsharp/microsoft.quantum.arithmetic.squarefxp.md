---
uid: Microsoft.Quantum.Arithmetic.SquareFxP
title: SquareFxP, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareFxP
qsharp.summary: Squares a fixed-point number.
ms.openlocfilehash: 8d08cb51e3a7ae892b23be0adbb7cdf3ee0f4de5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221882"
---
# <a name="squarefxp-operation"></a><span data-ttu-id="beb17-102">SquareFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="beb17-102">SquareFxP operation</span></span>

<span data-ttu-id="beb17-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="beb17-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="beb17-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="beb17-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="beb17-105">Kwadraty o stałej liczbie punktów.</span><span class="sxs-lookup"><span data-stu-id="beb17-105">Squares a fixed-point number.</span></span>

```qsharp
operation SquareFxP (fp : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="beb17-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="beb17-106">Input</span></span>

### <a name="fp--fixedpoint"></a><span data-ttu-id="beb17-107">FP: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="beb17-107">fp : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="beb17-108">Liczba stałych punktów.</span><span class="sxs-lookup"><span data-stu-id="beb17-108">Fixed-point number.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="beb17-109">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="beb17-109">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="beb17-110">Liczba stałych punktów wyników musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="beb17-110">Result fixed-point number, must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="beb17-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="beb17-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

