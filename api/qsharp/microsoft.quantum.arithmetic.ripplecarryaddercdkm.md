---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderCDKM
title: RippleCarryAdderCDKM, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderCDKM
qsharp.summary: Reversible, in-place ripple-carry addition of two integers.
ms.openlocfilehash: b08d8823fd539263205aca1ee15ee69adcb163b7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222103"
---
# <a name="ripplecarryaddercdkm-operation"></a>RippleCarryAdderCDKM, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Odwracalny, w miejscu Ripple — Dodawanie dwóch liczb całkowitych.

```qsharp
operation RippleCarryAdderCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

W przypadku dwóch $n $-bitowych liczb całkowitych zakodowanych w rejestrach LittleEndian `xs` i `ys` , a qubit, operacja oblicza sumę dwóch liczb całkowitych, w których $n $ najmniej znaczące bity wyniku są przechowywane, `ys` a bit przeprowadzenia jest XORed do qubit `carry` .

## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit rejestruje pierwszą liczbę całkowitą summand.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit rejestru kodowanie drugiej wartości całkowitej summand, został zmodyfikowany w celu przechowywania n najmniej znaczących bitów sum.


### <a name="carry--qubit"></a>Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Przenieś qubit, jest XORed z najbardziej znaczącym bitem kwoty.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Ta operacja ma takie same funkcje jak RippleCarryAdderD, ale używa tylko jednej pomocniczej qubit zamiast $n $.

## <a name="references"></a>Odwołania

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1