---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: Operacja _assertEqualOnBasisVector
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713155"
---
# <a name="_assertequalonbasisvector-operation"></a>Operacja _assertEqualOnBasisVector

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


Sprawdza, czy wynik zastosowania dwóch operacji `givenU` i `expectedU` do stanu podstawy jest taki sam. Stan podstawy jest opisany przez `basis` parametr.
Zobacz <xref:microsoft.quantum.extensions.fliptobasis> Funkcja, aby uzyskać więcej informacji na temat tego opisu.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="basis--int"></a>Podstawa: [int](xref:microsoft.quantum.lang-ref.int)[]

Stan bazowy określony przez identyfikator stanu podstawy pojedynczego qubit (0 <= ID <= 3) dla każdej z $n $ qubits.


### <a name="givenu--qubit--unit"></a>givenU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja na $n $ qubits do sprawdzenia.


### <a name="expectedu--qubit--unit-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja odwołania na $n $ qubits, że givenU jest porównywana z.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

