---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: Operacja _assertEqualOnBasisVector
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 041fecfa27ae5bd17fa8fdc89ce964f985f6124b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853581"
---
# <a name="_assertequalonbasisvector-operation"></a>Operacja _assertEqualOnBasisVector

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja odwołania na $n $ qubits, że givenU jest porównywana z.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

