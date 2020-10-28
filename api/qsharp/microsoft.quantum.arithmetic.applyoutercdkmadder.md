---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 5ec9d31252254e40efb22e06656294325b4cffcd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721569"
---
# <a name="applyoutercdkmadder-operation"></a>ApplyOuterCDKMAdder, operacja

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Odwracalna, w miejscu — Przenieś operację, która jest używana w operacji dodawania liczby całkowitej RippleCarryAdderCDKM poniżej.
W przypadku dwóch rejestrów qubit `xs` i `ys` o tej samej długości operacja stosuje sekwencję CNOT i CCNOT bram z qubits w `xs` i `ys` jako `xs` elementy docelowe.

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Pierwszy rejestr qubit zawierający kontrolki i obiekty docelowe.


### <a name="ys--littleendian"></a>YS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Drugi rejestr qubit, który przyczynia się do kontrolek.


### <a name="ancilla--qubit"></a>Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Ancilla qubit używany w RippleCarryAdderCDKM przeszedł do tej operacji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Dokumentacja

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. Kutin, David Petrie Moulton: "A New Quantum Ripple-przenieść obwód dodawania", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1