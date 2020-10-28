---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdder
title: ApplyInnerTTKAdder, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdder
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 23c1f6dcdf3894cf1b416efd922c9eed01ac8f85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721656"
---
# <a name="applyinnerttkadder-operation"></a>ApplyInnerTTKAdder, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Implementuje wewnętrzną funkcję dodawania dla operacji RippleCarryAdderTTK. Jest to operacja wewnętrzna, która jest sprzężona z zewnętrzną operacją do konstruowania pełnego dodającego.

```qsharp
operation ApplyInnerTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit rejestruje pierwsze całkowite dane wejściowe summand do RippleCarryAdderTTK.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register kodowanie drugiej liczby całkowitej summand danych wejściowych do RippleCarryAdderTTK.


### <a name="carry--qubit"></a>Przenieś: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Przenieś qubit, jest XORed z najbardziej znaczącym bitem kwoty.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Określona kontrolowana operacja korzysta z symetrii i wzajemnego anulowania operacji w celu usprawnienia implementacji domyślnej, która dodaje kontrolkę do każdej operacji.

## <a name="references"></a>Dokumentacja

- Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Podłączanie jednostek Quantum i niepowiązane wentylatory", informacje o Quantum i obliczenia, vol. 10, 2010.
  https://arxiv.org/abs/0910.2530