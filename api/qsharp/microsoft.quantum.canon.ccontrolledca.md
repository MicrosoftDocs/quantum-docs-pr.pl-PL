---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: cc1a783dfbf97afae50f4b42e66cba2b2a2ec833
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207432"
---
# <a name="ccontrolledca-function"></a>CControlledCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki. Jeśli `false` nie, nic się nie dzieje.
Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit--is-adj--ctl"></a>op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Operacja, która ma być stosowana warunkowo.



## <a name="output--boolt--unit--is-adj--ctl"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)