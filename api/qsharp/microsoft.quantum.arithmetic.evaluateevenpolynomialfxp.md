---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: e49a6d47553a60766b561525e8cfa37e95fda9e8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721200"
---
# <a name="evaluateevenpolynomialfxp-operation"></a><span data-ttu-id="a2b90-102">EvaluateEvenPolynomialFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="a2b90-102">EvaluateEvenPolynomialFxP operation</span></span>

<span data-ttu-id="a2b90-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="a2b90-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="a2b90-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a2b90-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a2b90-105">Oblicza parzysty wielomian w reprezentacji ustalonej.</span><span class="sxs-lookup"><span data-stu-id="a2b90-105">Evaluates an even polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="a2b90-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a2b90-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="a2b90-107">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a2b90-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a2b90-108">Współczynniki wielomianu parzystego jako tablicę podwójną, czyli tablicę $ [a_0, a_1,..., a_k] $ dla parzystego wielomianu $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2K} $.</span><span class="sxs-lookup"><span data-stu-id="a2b90-108">Coefficients of the even polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the even polynomial $P(x) = a_0 + a_1 x^2 + \cdots + a_k x^{2k}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="a2b90-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a2b90-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a2b90-110">Wprowadź liczbę stałych punktów, dla której ma zostać obliczony wielomian.</span><span class="sxs-lookup"><span data-stu-id="a2b90-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="a2b90-111">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="a2b90-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="a2b90-112">Liczba stałych punktów wyjściowych, które będą przechowywane $P (x) $.</span><span class="sxs-lookup"><span data-stu-id="a2b90-112">Output fixed-point number which will hold $P(x)$.</span></span> <span data-ttu-id="a2b90-113">Musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="a2b90-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a2b90-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a2b90-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

