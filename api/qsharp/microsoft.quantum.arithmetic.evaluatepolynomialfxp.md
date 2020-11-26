---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 4f6ed4b34af2e63dd8ee31fb9b93119e06e3ecbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223191"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="f2aa5-102">EvaluatePolynomialFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="f2aa5-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="f2aa5-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="f2aa5-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="f2aa5-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="f2aa5-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="f2aa5-105">Oblicza wielomian w reprezentacji ustalonej.</span><span class="sxs-lookup"><span data-stu-id="f2aa5-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f2aa5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f2aa5-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="f2aa5-107">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f2aa5-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f2aa5-108">Współczynniki wielomianu jako tablicę podwójną, czyli tablicę $ [a_0, a_1,..., a_d] $ dla wielomianu $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.</span><span class="sxs-lookup"><span data-stu-id="f2aa5-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="f2aa5-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f2aa5-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f2aa5-110">Wprowadź liczbę stałych punktów, dla której ma zostać obliczony wielomian.</span><span class="sxs-lookup"><span data-stu-id="f2aa5-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="f2aa5-111">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="f2aa5-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="f2aa5-112">Liczba stałych punktów wyjściowych, które będą przechowywane $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="f2aa5-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="f2aa5-113">Musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="f2aa5-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2aa5-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2aa5-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

