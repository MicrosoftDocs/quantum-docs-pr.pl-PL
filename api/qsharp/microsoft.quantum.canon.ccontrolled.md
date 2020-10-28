---
uid: Microsoft.Quantum.Canon.CControlled
title: CControlled, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlled
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens.
ms.openlocfilehash: a155b00806b17258b3f87629659bc7d786e4e11d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716590"
---
# <a name="ccontrolled-function"></a>CControlled, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Po podaniu operacji operacja zwraca nową operację, która stosuje tę wartość, jeśli jest spełniony parametr klasycznej kontrolki. Jeśli `false` nie, nic się nie dzieje.

```qsharp
function CControlled<'T> (op : ('T => Unit)) : ((Bool, 'T) => Unit)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit"></a>op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma być stosowana warunkowo.



## <a name="output--boolt--unit"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool), t) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Nowa operacja, która jest operacją, jeśli klasyczny bit kontroli ma wartość true.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. CControlledC](xref:Microsoft.Quantum.Canon.CControlledC)
- [Microsoft. Quantum. Canon. CControlledA](xref:Microsoft.Quantum.Canon.CControlledA)
- [Microsoft. Quantum. Canon. CControlledCA](xref:Microsoft.Quantum.Canon.CControlledCA)