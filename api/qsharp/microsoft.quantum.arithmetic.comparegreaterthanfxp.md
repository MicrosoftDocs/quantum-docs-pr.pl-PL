---
uid: Microsoft.Quantum.Arithmetic.CompareGreaterThanFxP
title: CompareGreaterThanFxP, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareGreaterThanFxP
qsharp.summary: Compares two fixed-point numbers stored in quantum registers, and controls a flip on the result.
ms.openlocfilehash: bd3bcedd7a4a81fc600f7f4b6bdf1d2a797abbd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721296"
---
# <a name="comparegreaterthanfxp-operation"></a>CompareGreaterThanFxP, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Porównuje dwie stałe numery przechowywane w rejestrach Quantum i kontroluje odbicie w wyniku.

```qsharp
operation CompareGreaterThanFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Pierwsza stała liczba do porównania.


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Druga liczba stałych punktów do porównania.


### <a name="result--qubit"></a>wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Wynik porównania. Zostanie odwrócony, jeśli `fp1 > fp2` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Bieżąca implementacja wymaga, aby dwie stałe numery miały tę samą pozycję punktu i taką samą liczbę qubits.