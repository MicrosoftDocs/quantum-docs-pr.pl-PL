---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718248"
---
# <a name="applyifa-operation"></a>ApplyIfA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację przylegającej do stanu na klasycznym.

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Opis

Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` . Jeśli `false` nie, nic się nie dzieje z `target` .
Sufiks `A` wskazuje, że operacja, która ma zostać zastosowana, to przylegający.

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-adj"></a>op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja, która ma być stosowana warunkowo.


### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

wartość logiczna, która kontroluje, czy operacja jest stosowana, czy nie.


### <a name="target--t"></a>element docelowy: 'T

Dane wejściowe, do których zostanie zastosowana operacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyIfC](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [Microsoft. Quantum. Canon. ApplyIfA](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [Microsoft. Quantum. Canon. ApplyIfCA](xref:Microsoft.Quantum.Canon.ApplyIfCA)