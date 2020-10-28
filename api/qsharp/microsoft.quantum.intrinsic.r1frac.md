---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720900"
---
# <a name="r1frac-operation"></a>R1Frac, operacja

Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)

Package [](https://nuget.org/packages/)


Stosuje obrót o stanie $ \ket {1} $ przez kąt określony jako ułamek dyadic.

\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \pi k/2 ^ n}).
\end{align}

> [!WARNING]
> Ta operacja używa **przeciwległej** Konwencji podpisywania z @"microsoft.quantum.intrinsic.r" i nie obejmuje współczynnika $1/2 $ dołączonego przez @"microsoft.quantum.intrinsic.r1" .

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="numerator--int"></a>Licznik: [int](xref:microsoft.quantum.lang-ref.int)

Licznik w reprezentacji dyadic ułamek kąta, do którego ma zostać obrócony qubit.


### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)

Potęga dwóch określająca mianownik kąta, do którego ma zostać obrócony qubit.


### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, do którego należy zastosować bramę.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Równoważne:

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```