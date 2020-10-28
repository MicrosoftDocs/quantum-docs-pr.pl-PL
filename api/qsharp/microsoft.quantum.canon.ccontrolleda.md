---
uid: Microsoft.Quantum.Canon.CControlledA
title: CControlledA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716585"
---
# <a name="ccontrolleda-function"></a>CControlledA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki. Jeśli `false` nie, nic się nie dzieje.
Modyfikator `A` wskazuje, że operacja jest sąsiedni.

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-adj"></a>op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja, która ma być stosowana warunkowo.



## <a name="output--boolt--unit-adj"></a>Wynik: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)