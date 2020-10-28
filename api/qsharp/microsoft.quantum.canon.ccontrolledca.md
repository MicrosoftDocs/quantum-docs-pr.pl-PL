---
uid: Microsoft.Quantum.Canon.CControlledCA
title: CControlledCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledCA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 20a8c9ccf931261f7bc6e347ccc144c92f0d0545
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716571"
---
# <a name="ccontrolledca-function"></a>CControlledCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki. Jeśli `false` nie, nic się nie dzieje.
Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.

```qsharp
function CControlledCA<'T> (op : ('T => Unit is Ctl + Adj)) : ((Bool, 'T) => Unit is Ctl + Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-ctl--adj"></a>op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Operacja, która ma być stosowana warunkowo.



## <a name="output--boolt--unit-ctl--adj"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool), t) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + korekta

Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. CControlled](xref:Microsoft.Quantum.Canon.CControlled)