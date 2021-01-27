---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843288"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ta operacja sprawdza, czy liczba całkowita reprezentowana przez rejestr qubits jest większa niż inna liczba całkowita, stosując XOR wyniku do qubit wyjściowego.

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Dwie liczby całkowite `x` i `y` zapisane w rejestrach qubit o równym rozmiarze są sprawdzane, czy są one spełnione `x > y` . W przypadku wartości true wartość 1 jest XORed do qubit wyjściowego. W przeciwnym razie wartość 0 jest XORed do qubit wyjściowego.
Innymi słowy, ta operacja może być reprezentowana przez jednostkę $ $ \begin{align} U\ket {x} \ KET {y} \ KET {z} = \ket{x}\ket{y}\ket{z\oplus (x>y)}.
\end{align} $ $

## <a name="input"></a>Dane wejściowe

### <a name="x--littleendian"></a>x: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Pierwszy numer, który ma być porównywany w `LittleEndian` formacie w rejestrze qubit.


### <a name="y--littleendian"></a>y: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Druga liczba do porównania przechowywanych w `LittleEndian` formacie w rejestrze qubit.


### <a name="output--qubit"></a>wynik: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, który przechowuje wynik porównania $x>y $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Odwołania

- Nowy program Quantum Ripple — przeniesienie obwodu dodawania Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184