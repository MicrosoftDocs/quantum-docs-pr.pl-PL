---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: RippleCarryAdderTTK, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719565"
---
# <a name="ripplecarryadderttk-operation"></a>RippleCarryAdderTTK, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Odwracalny, w miejscu Ripple — Dodawanie dwóch liczb całkowitych.
W przypadku dwóch $n $-bitowych liczb całkowitych zakodowanych w rejestrach LittleEndian `xs` i `ys` , a qubit, operacja oblicza sumę dwóch liczb całkowitych, w których $n $ najmniej znaczące bity wyniku są przechowywane, `ys` a bit przeprowadzenia jest XORed do qubit `carry` .

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit rejestruje pierwszą liczbę całkowitą summand.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit rejestru kodowanie drugiej wartości całkowitej summand, jest modyfikowany do przechowywania $n $ najmniej znaczących bitów sum.


### <a name="carry--qubit"></a>Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Przenieś qubit, jest XORed z najbardziej znaczącym bitem kwoty.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Ta operacja ma takie same funkcje jak RippleCarryAdderD i, RippleCarryAdderCDKM, ale nie używa żadnych qubits Ancilla.

## <a name="references"></a>Dokumentacja

- Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530