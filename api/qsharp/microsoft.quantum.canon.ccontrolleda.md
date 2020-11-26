---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: cb72ca5b3dab99b9ee8a994ba9fde46e0eae5594
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207517"
---
# <a name="ccontrolleda-function"></a>CControlledA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki. Jeśli `false` nie, nic się nie dzieje.
Modyfikator `A` wskazuje, że operacja jest sąsiedni.

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit--is-adj"></a>op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja, która ma być stosowana warunkowo.



## <a name="output--boolt--unit--is-adj"></a>Wynik: ([bool](xref:microsoft.quantum.lang-ref.bool), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)