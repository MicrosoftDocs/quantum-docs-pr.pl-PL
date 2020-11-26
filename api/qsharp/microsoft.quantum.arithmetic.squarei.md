---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: 79a431d411c4ffd502fb5338b5396341fd63aea8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221865"
---
# <a name="squarei-operation"></a>SquareI, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Oblicza kwadrat liczby całkowitej `xs` w `result` , która musi być początkowo zerowa.

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-bit Number do kwadratu (LittleEndian)


### <a name="result--littleendian"></a>wynik: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

wynik $2n $-bit (LittleEndian) musi być w stanie $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Używa standardowej metody Shift-and-Add do obliczania kwadratu. Zapisuje $n-$1 qubits w porównaniu do rozwiązania prostego przesyłania dalej, które najpierw kopiuje wyjście XS przed zastosowaniem zwykłego mnożnika, a następnie cofa operację kopiowania.