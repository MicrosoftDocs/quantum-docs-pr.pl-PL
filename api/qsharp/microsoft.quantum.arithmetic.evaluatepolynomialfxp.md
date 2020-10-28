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
# <a name="evaluatepolynomialfxp-operation"></a>EvaluatePolynomialFxP, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Oblicza wielomian w reprezentacji ustalonej.

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="coefficients--double"></a>współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]

Współczynniki wielomianu jako tablicę podwójną, czyli tablicę $ [a_0, a_1,..., a_d] $ dla wielomianu $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Wprowadź liczbę stałych punktów, dla której ma zostać obliczony wielomian.


### <a name="result--fixedpoint"></a>wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Liczba stałych punktów wyjściowych, które będą przechowywane $P (x) $. Musi być w stanie $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

