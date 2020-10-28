---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721185"
---
# <a name="evaluatepolynomialfxp-operation"></a><span data-ttu-id="a40a8-102">EvaluatePolynomialFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="a40a8-102">EvaluatePolynomialFxP operation</span></span>

<span data-ttu-id="a40a8-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a40a8-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a40a8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a40a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a40a8-105">Oblicza wielomian w reprezentacji ustalonej.</span><span class="sxs-lookup"><span data-stu-id="a40a8-105">Evaluates a polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="a40a8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a40a8-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a40a8-107">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a40a8-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a40a8-108">Współczynniki wielomianu jako tablicę podwójną, czyli tablicę $ [a_0, a_1,..., a_d] $ dla wielomianu $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.</span><span class="sxs-lookup"><span data-stu-id="a40a8-108">Coefficients of the polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_d]$ for the polynomial $P(x) = a_0 + a_1 x + \cdots + a_d x^d$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="a40a8-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a40a8-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a40a8-110">Wprowadź liczbę stałych punktów, dla której ma zostać obliczony wielomian.</span><span class="sxs-lookup"><span data-stu-id="a40a8-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="a40a8-111">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a40a8-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a40a8-112">Liczba stałych punktów wyjściowych, które będą przechowywane $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="a40a8-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="a40a8-113">Musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a40a8-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a40a8-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a40a8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

