---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: fb67455dadbc7a2f38880581f0e413a747faa8ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721077"
---
# <a name="incrementphasebyinteger-operation"></a>IncrementPhaseByInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Zwiększa niepodpisany rejestr Quantum przez klasyczną liczbę całkowitą, używając rotacji faz.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="description"></a>Opis

Załóżmy, że `target` koduje liczbę całkowitą bez znaku $x $ w kodowaniu little-endian i która `increment` jest równa $a $.
Następnie ta operacja implementuje moduł $ \ket{x} \mapsto \ket{x + a} $, w którym jest wykonywane dzielenie modulo $2 ^ n $, gdzie $n = \texttt{Length (target!)} $.

## <a name="input"></a>Dane wejściowe

### <a name="increment--int"></a>Zwiększ: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita, przez którą `target` jest zwiększana wartość.


### <a name="target--phaselittleendian"></a>obiekt docelowy: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Rejestr Quantum zarejestruje liczbę całkowitą bez znaku przy użyciu kodowania little-endian na zasadzie podwójnej (QFT).



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Należy pamiętać, że uproszczono obwód, ponieważ przyrost jest klasyczną stałą, a nie rejestrem Quantum.

Zobacz rysunek na [ stronie 6 of ArXiv: Quant-pH/0008033v1 ](https://arxiv.org/pdf/quant-ph/0008033.pdf#page=6) dla diagramu obwodu i wyjaśnienie.

## <a name="references"></a>Dokumentacja

- [*Thomas G. Draper* , ArXiv: Quant-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)