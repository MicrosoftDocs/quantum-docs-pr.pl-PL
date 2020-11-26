---
uid: Microsoft.Quantum.Characterization.ApplyHadamardTestOnSingleRegister
title: ApplyHadamardTestOnSingleRegister, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ApplyHadamardTestOnSingleRegister
qsharp.summary: ''
ms.openlocfilehash: d61912d3681f7a6462f4b25aaf800483aecbee01
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204457"
---
# <a name="applyhadamardtestonsingleregister-operation"></a>ApplyHadamardTestOnSingleRegister, operacja

Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyHadamardTestOnSingleRegister (phaseShift : Bool, commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Dane wejściowe

### <a name="phaseshift--bool"></a>phaseShift: [bool](xref:microsoft.quantum.lang-ref.bool)




### <a name="commonpreparation--qubit--unit--is-adj"></a>commonPreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą




### <a name="preparation1--qubit--unit--is-adj--ctl"></a>preparation1: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL




### <a name="preparation2--qubit--unit--is-adj--ctl"></a>preparation2: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL




### <a name="register--qubit"></a>Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

