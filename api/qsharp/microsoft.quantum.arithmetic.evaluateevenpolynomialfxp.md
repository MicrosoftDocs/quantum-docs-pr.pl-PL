---
uid: Microsoft.Quantum.Arithmetic.EvaluateEvenPolynomialFxP
title: EvaluateEvenPolynomialFxP, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluateEvenPolynomialFxP
qsharp.summary: Evaluates an even polynomial in a fixed-point representation.
ms.openlocfilehash: c3129cb796a344f7ad38a585183db285d48892bf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843229"
---
# <a name="evaluateevenpolynomialfxp-operation"></a>EvaluateEvenPolynomialFxP, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Oblicza parzysty wielomian w reprezentacji ustalonej.

```qsharp
operation EvaluateEvenPolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="coefficients--double"></a>współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]

Współczynniki wielomianu parzystego jako tablicę podwójną, czyli tablicę $ [a_0, a_1,..., a_k] $ dla parzystego wielomianu $P (x) = a_0 + a_1 x ^ 2 + \cdots + a_k x ^ {2K} $.


### <a name="fpx--fixedpoint"></a>FPX: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Wprowadź liczbę stałych punktów, dla której ma zostać obliczony wielomian.


### <a name="result--fixedpoint"></a>wynik: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Liczba stałych punktów wyjściowych, które będą przechowywane $P (x) $. Musi być w stanie $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

