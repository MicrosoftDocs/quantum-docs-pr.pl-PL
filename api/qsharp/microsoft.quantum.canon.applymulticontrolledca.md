---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717962"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje mnożenie kontrolowanej wersji operacji pojedynczo kontrolowanej.
Modyfikator `CA` wskazuje, że operacje pojedynczego qubit są kontrolowane i sąsiadujące.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="singlycontrolledop--qubit--unit-adj"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja kontrolowana przy użyciu jednej qubit.
Pierwszy qubit w argumencie operacji założono, że jest formantem, a reszta przyjmuje wartość Target qubits.
`ApplyMultiControlled` zawsze wywołuje `singlyControlledOp` z argumentem o długości co najmniej 1.


### <a name="ccnot--ccnotop"></a>ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)

Kontrolowana Brama nie może być używana do celów konstrukcyjnych.


### <a name="controls--qubit"></a>kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits, które `singlyControlledOp` mają być kontrolowane.
Długość `controls` musi być równa co najmniej 1.


### <a name="targets--qubit"></a>elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Docelowy qubits, na którym `singlyControlledOp` działa.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Ta operacja używa tylko czystego Ancilla qubits.

Aby uzyskać informacje na temat diagramu wyjaśnień i obwodów, zobacz rysunek 4,10, sekcja 4,3 w Nielsen & Czuang

## <a name="references"></a>Dokumentacja

- [*Michael a. Nielsen, Tomasz L. Czuang* , obliczenia Quantum i informacje o Quantum](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)