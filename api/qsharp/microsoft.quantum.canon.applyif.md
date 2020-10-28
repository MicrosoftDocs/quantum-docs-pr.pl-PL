---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718245"
---
# <a name="applyif-operation"></a>ApplyIf, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację warunkową przy użyciu klasycznego bitu.

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a>Opis

Dana operacja `op` i wartość bitowa `bit` mają zastosowanie do elementu `op` `target` if `bit` is `true` . Jeśli `false` nie, nic się nie dzieje z `target` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit"></a>op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

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