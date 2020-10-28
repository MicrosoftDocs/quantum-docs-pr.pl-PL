---
uid: Microsoft.Quantum.Arithmetic.IncrementByInteger
title: IncrementByInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: 363d48d697e3b2dad4d4896e6b1e701864649d9b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721113"
---
# <a name="incrementbyinteger-operation"></a>IncrementByInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Zwiększa niepodpisany rejestr Quantum przez klasyczną liczbę całkowitą, używając rotacji faz.

```qsharp
operation IncrementByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

Załóżmy, że `target` koduje liczbę całkowitą bez znaku $x $ w kodowaniu little-endian i która `increment` jest równa $a $.
Następnie ta operacja implementuje moduł $ \ket{x} \mapsto \ket{x + a} $, w którym jest wykonywane dzielenie modulo $2 ^ n $, gdzie $n = \texttt{Length (target!)} $.

## <a name="input"></a>Dane wejściowe

### <a name="increment--int"></a>Zwiększ: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita, przez którą `target` jest zwiększana wartość.


### <a name="target--littleendian"></a>obiekt docelowy: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Rejestr Quantum zakodowania liczbę całkowitą bez znaku przy użyciu kodowania little-endian.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

