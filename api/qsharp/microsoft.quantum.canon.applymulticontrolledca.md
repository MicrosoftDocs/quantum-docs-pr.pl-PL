---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 28797583c23e21eb4bcae996a34c70ee06c6dbe8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209285"
---
# <a name="applymulticontrolledca-operation"></a>ApplyMultiControlledCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje mnożenie kontrolowanej wersji operacji pojedynczo kontrolowanej.
Modyfikator `CA` wskazuje, że operacje pojedynczego qubit są kontrolowane i sąsiadujące.

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="singlycontrolledop--qubit--unit--is-adj"></a>singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

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

## <a name="references"></a>Odwołania

- [*Michael a. Nielsen, Tomasz L. Czuang*, obliczenia Quantum i informacje o Quantum](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyMultiControlledC](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)