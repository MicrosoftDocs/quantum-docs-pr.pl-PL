---
uid: Microsoft.Quantum.Arithmetic.GreaterThan
title: GreaterThan, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: GreaterThan
qsharp.summary: Applies a greater-than comparison between two integers encoded into qubit registers, flipping a target qubit based on the result of the comparison.
ms.openlocfilehash: b7214b43dacd07b4750be4b681f30937185ac953
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721137"
---
# <a name="greaterthan-operation"></a>GreaterThan, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Stosuje większe niż porównanie dwóch liczb całkowitych zakodowanych w rejestrach qubit, przerzucając docelowy qubit na podstawie wyniku porównania.

```qsharp
operation GreaterThan (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, result : Qubit) : Unit
```


## <a name="description"></a>Opis

Wykonuje ściśle większe niż porównanie dwóch liczb całkowitych, $x $ i $y $, zakodowane w qubit rejestruje i YS. Jeśli $x > y $, wynik qubit zostanie przerzucony, w przeciwnym razie wynik qubit spowoduje zachowanie stanu.

## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Zarejestruj pierwszą liczbę całkowitą $x $.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

LittleEndian qubit Register kodowanie drugiej liczby całkowitej $y $.


### <a name="result--qubit"></a>wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pojedyncze qubit, które zostaną przerzucone, jeśli $x > y $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Używa lew, która $x-y = (x ' + y) ' $, gdzie ' oznacza uzupełnienie jednego.

## <a name="references"></a>Dokumentacja

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1

- Thomas Haener, Martin Roetteler, krysta M. Svore: "factoring using 2n + 2 qubits with modułowe mnożenia", 2016 https://arxiv.org/abs/1611.07995