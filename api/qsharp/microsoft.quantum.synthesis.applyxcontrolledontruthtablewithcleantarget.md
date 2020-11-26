---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: ApplyXControlledOnTruthTableWithCleanTarget, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 904ff7e2e7e81ee966846af120e9427f4e92301c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203267"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>ApplyXControlledOnTruthTableWithCleanTarget, operacja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje @"microsoft.quantum.intrinsic.x" operację na `target` , jeśli funkcja logiczna `func` zwróci wartość true dla klasycznego przypisania w `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Opis

Ta operacja implementuje szczególny przypadek @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , w którym element docelowy qubit jest znany jako w stanie $ \ket {0} $.

Implementacja wykorzystuje @"microsoft.quantum.intrinsic.cnot" @"microsoft.quantum.intrinsic.r1" bramy i.  Implementacja sąsiedniej operacji jest zoptymalizowana i używa obliczeń opartych na pomiarach.

## <a name="input"></a>Dane wejściowe

### <a name="func--bigint"></a>Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Tabela wartości logicznych prawdy reprezentowana jako duża liczba całkowita


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr kontroli qubits


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Element docelowy qubit (musi być w stanie $ \ket {0} $)



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. synteza. ApplyXControlledOnTruthTable](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)