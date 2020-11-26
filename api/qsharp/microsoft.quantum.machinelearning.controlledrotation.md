---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 1e664b470caeba656ea4a73f70bbc0ef5fe76f7e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196569"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Pakiet: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Opisuje ukierunkowane rotacje w warunkach jego celu i indeksów kontroli, osi obrotu i indeksu do wektora parametru modelu.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="targetindex--int"></a>TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indeks qubit docelowego dla tego kontrolowanego obrotu.
### <a name="controlindices--int"></a>ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica indeksów qubit dla tego obrotu.
### <a name="axis--pauli"></a>Oś: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Oś dla tego obrotu.
### <a name="parameterindex--int"></a>ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)

Indeks do wektora parametru modelu opisującego kąt tego obrotu.

## <a name="remarks"></a>Uwagi

Obrót niekontrolowany może być reprezentowany przez ustawienie `ControlIndices` do pustej tablicy indeksów `new Int[0]` .