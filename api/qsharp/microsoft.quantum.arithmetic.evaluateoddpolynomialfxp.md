---
uid: Microsoft.Quantum.Arithmetic.EvaluateOddPolynomialFxP
title: EvaluateOddPolynomialFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateOddPolynomialFxP
qsharp.summary: Evaluates an odd polynomial in a fixed-point representation.
ms.openlocfilehash: 852e986cd09c3b2e31263f53e381d9da73298415
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846660"
---
# <a name="evaluateoddpolynomialfxp-operation"></a><span data-ttu-id="9dc86-102">EvaluateOddPolynomialFxP, operacja</span><span class="sxs-lookup"><span data-stu-id="9dc86-102">EvaluateOddPolynomialFxP operation</span></span>

<span data-ttu-id="9dc86-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="9dc86-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="9dc86-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="9dc86-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="9dc86-105">Oblicza nieparzysty wielomian w reprezentacji ustalonej.</span><span class="sxs-lookup"><span data-stu-id="9dc86-105">Evaluates an odd polynomial in a fixed-point representation.</span></span>

```qsharp
operation EvaluateOddPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9dc86-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9dc86-106">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="9dc86-107">współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9dc86-107">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9dc86-108">Współczynniki nieparzystego wielomianu jako tablicy podwójnej, tj. Array $ [a_0, a_1,..., a_k] $ dla nieparzystego wielomianu $P (x) = a_0 x + a_1 x ^ 3 + \cdots + a_k x ^ {2K + 1} $.</span><span class="sxs-lookup"><span data-stu-id="9dc86-108">Coefficients of the odd polynomial as a double array, i.e., the array $[a_0, a_1, ..., a_k]$ for the odd polynomial $P(x) = a_0 x + a_1 x^3 + \cdots + a_k x^{2k+1}$.</span></span>


### <a name="fpx--fixedpoint"></a><span data-ttu-id="9dc86-109">FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9dc86-109">fpx : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9dc86-110">Wprowadź liczbę stałych punktów, dla której ma zostać obliczony wielomian.</span><span class="sxs-lookup"><span data-stu-id="9dc86-110">Input fixed-point number for which to evaluate the polynomial.</span></span>


### <a name="result--fixedpoint"></a><span data-ttu-id="9dc86-111">wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="9dc86-111">result : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="9dc86-112">Wyjściowa liczba zmiennoprzecinkowa, która będzie zawierać P (x).</span><span class="sxs-lookup"><span data-stu-id="9dc86-112">Output fixed-point number which will hold P(x).</span></span> <span data-ttu-id="9dc86-113">Musi być w stanie $ \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="9dc86-113">Must be in state $\ket{0}$ initially.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9dc86-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9dc86-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

