---
uid: Microsoft.Quantum.Canon.ConjugatedByC
title: ConjugatedByC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedByC
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c4c381e40c5a941487bcf78ebe5339574aedb45d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716459"
---
# <a name="conjugatedbyc-function"></a>ConjugatedByC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana operacja zewnętrzna i wewnętrzna zwraca nową operację, która jest sprzężona z operacją wewnętrzną przez operację zewnętrzną.

```qsharp
function ConjugatedByC<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Ctl)) : ('T => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="outeroperation--t--unit-adj"></a>outerOperation: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja $U $, która powinna być używana do sprzężonia $V $. Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.


### <a name="inneroperation--t--unit-ctl"></a>innerOperation: t => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Operacja $V $ jest sprzężona.



## <a name="output--t--unit-ctl"></a>Dane wyjściowe: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Nowa operacja, której akcja jest reprezentowana przez jednostkę $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementu docelowego, na którym działa każda z wewnętrznych i zewnętrznych operacji.

## <a name="remarks"></a>Uwagi

Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ConjugatedBy](xref:Microsoft.Quantum.Canon.ConjugatedBy)
- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)