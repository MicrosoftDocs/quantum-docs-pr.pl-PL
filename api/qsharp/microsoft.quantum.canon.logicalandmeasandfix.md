---
uid: Microsoft.Quantum.Canon.LogicalANDMeasAndFix
title: LogicalANDMeasAndFix, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: LogicalANDMeasAndFix
qsharp.summary: Computes the logical AND of multiple qubits.
ms.openlocfilehash: 86e4b9a8c6ed5f4f56db0ceefc8051d34e911c4c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715927"
---
# <a name="logicalandmeasandfix-operation"></a>LogicalANDMeasAndFix, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Oblicza wartość logiczną i wiele qubits.

```qsharp
operation LogicalANDMeasAndFix (ctrlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="ctrlregister--qubit"></a>ctrlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits dane wejściowe do bramy z wieloma danymi wejściowymi i.


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, w którym są zapisywane dane wyjściowe i. Przyjęto założenie, że zawsze zaczyna się w stanie $ \ket {0} $.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Gdy `ctrlRegister` ma dokładnie $2 $ qubits, jest to równoważne z `CCNOT` operacją, ale faza z fazą $e ^ {i \ pi/2} $ w $ \ket {001} $ i $-e ^ {i \ pi/2} $ w $ \ket {101} $ i $ \ket {011} $.
Sąsiednie rozwiązanie jest również metodą mierzenia i naprawiania, która jest odwrotnością oryginalnej operacji tylko w specjalnych przypadkach (zobacz odwołania), ale używa mniejszej liczby bram T-.

## <a name="references"></a>Dokumentacja

- [*Craig Gidney* , 1709,06648](https://arxiv.org/abs/1709.06648)