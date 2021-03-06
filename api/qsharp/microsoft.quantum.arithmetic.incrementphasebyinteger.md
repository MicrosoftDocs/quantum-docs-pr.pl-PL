---
uid: Microsoft.Quantum.Arithmetic.IncrementPhaseByInteger
title: IncrementPhaseByInteger, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementPhaseByInteger
qsharp.summary: Increments an unsigned quantum register by a classical integer, using phase rotations.
ms.openlocfilehash: cc7922b2940cb979394958d5eb4e9933144eb062
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843146"
---
# <a name="incrementphasebyinteger-operation"></a>IncrementPhaseByInteger, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwiększa niepodpisany rejestr Quantum przez klasyczną liczbę całkowitą, używając rotacji faz.

```qsharp
operation IncrementPhaseByInteger (increment : Int, target : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
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

## <a name="references"></a>Odwołania

- [*Thomas G. Draper*, ArXiv: Quant-pH/0008033](https://arxiv.org/pdf/quant-ph/0008033v1.pdf)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. arytmetyczne. IncrementByInteger](xref:Microsoft.Quantum.Arithmetic.IncrementByInteger)