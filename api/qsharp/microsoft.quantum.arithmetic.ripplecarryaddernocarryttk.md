---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderNoCarryTTK
title: RippleCarryAdderNoCarryTTK, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderNoCarryTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers without carry out.
ms.openlocfilehash: 59451b4f5c992f900a27139332059af7427b9b93
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719580"
---
# <a name="ripplecarryaddernocarryttk-operation"></a>RippleCarryAdderNoCarryTTK, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Odwracalny, w miejscu Ripple — Dodawanie dwóch liczb całkowitych bez przeprowadzenia.

```qsharp
operation RippleCarryAdderNoCarryTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Opis

W przypadku dwóch $n $-bitowych liczb całkowitych zakodowanych w rejestrach LittleEndian `xs` i `ys` , operacja oblicza sumę dwóch liczb całkowitych modulo $2 ^ n $, gdzie $n $ jest rozmiarem bitowym danych wejściowych `xs` i `ys` . Nie jest obliczany bit przeprowadzenia.

## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit rejestruje pierwszą liczbę całkowitą summand.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit rejestru kodowanie drugiej wartości całkowitej summand, jest modyfikowany do przechowywania $n $ najmniej znaczących bitów sum.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Ta operacja ma takie same funkcje jak RippleCarryAdderTTK, ale nie zwraca bitu przenoszenia.

## <a name="references"></a>Dokumentacja

- Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530