---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: d52da4092f16d43ab9d08b03f798a4d6789c7348
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721197"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="3e386-102">EvaluateOddPolynomialFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="3e386-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="3e386-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3e386-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3e386-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e386-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e386-105">Oblicza nieparzysty wielomian w reprezentacji ustalonej.</span><span class="sxs-lookup"><span data-stu-id="3e386-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a><span data-ttu-id="3e386-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3e386-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="3e386-107">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="3e386-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="3e386-108">Współczynniki nieparzystego wielomianu jako tablicy podwójnej, tj. Array $ [a_0, a_1,..., a_k] $ dla nieparzystego wielomianu $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2K + 1} $.</span><span class="sxs-lookup"><span data-stu-id="3e386-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="3e386-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="3e386-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="3e386-110">Wprowadź liczbę stałych punktów, dla której ma zostać obliczony wielomian.</span><span class="sxs-lookup"><span data-stu-id="3e386-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="3e386-111">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="3e386-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="3e386-112">Wyjściowa liczba zmiennoprzecinkowa, która będzie zawierać P (x).</span><span class="sxs-lookup"><span data-stu-id="3e386-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="3e386-113">Musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="3e386-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e386-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e386-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

