---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: e16254154909eb844164538acb7b82fedc11f86a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718236"
---
# <a name="applyifc-operation"></a>ApplyIfC, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację z możliwością kontrolowania dla klasycznego bitu.

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Opis

Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` . Jeśli `false` nie, nic się nie dzieje z `target` .
Sufiks `C` wskazuje, że operacja do zastosowania jest sterowana.

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-ctl"></a>op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)

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