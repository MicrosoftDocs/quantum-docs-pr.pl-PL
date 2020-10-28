---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: e4f38e9bb54839076b817f6e61e96ca6a550576b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718389"
---
# <a name="applyccnotchain-operation"></a>ApplyCCNOTChain, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Implementuje kaskadowe bramy CCNOT kontrolowane na odpowiednich bitach dwóch rejestrów qubit, działając na następnym qubit jednego z rejestrów.
Począwszy od qubits na pozycji 0 w obu rejestrach jako kontrolki, CCNOT jest zastosowany do qubit na pozycji 1 rejestru docelowego, a następnie kontrolowane przez qubits na pozycji 1 działającej na qubit w pozycji 2 w rejestrze docelowym itd., kończąc z akcją na docelowym qubit na pozycji `Length(nQubits)-1` .

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="register--qubit"></a>Rejestr: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubit używany tylko w kontrolkach.


### <a name="targets--qubit"></a>elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr qubit używany w kontrolkach i jako element docelowy.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Docelowy rejestr qubit musi mieć jeden qubit więcej niż inny rejestr.