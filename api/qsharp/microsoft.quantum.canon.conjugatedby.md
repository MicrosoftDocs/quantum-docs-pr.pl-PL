---
uid: Microsoft.Quantum.Canon.ConjugatedBy
title: ConjugatedBy, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ConjugatedBy
qsharp.summary: Given outer and inner operations, returns a new operation that conjugates the inner operation by the outer operation.
ms.openlocfilehash: c11e6b2cc97e682bf4fe266997f60ce69e87ba96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840877"
---
# <a name="conjugatedby-function"></a>ConjugatedBy, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana operacja zewnętrzna i wewnętrzna zwraca nową operację, która jest sprzężona z operacją wewnętrzną przez operację zewnętrzną.

```qsharp
function ConjugatedBy<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit)) : ('T => Unit)
```


## <a name="input"></a>Dane wejściowe

### <a name="outeroperation--t--unit--is-adj"></a>outerOperation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja $U $, która powinna być używana do sprzężonia $V $. Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.


### <a name="inneroperation--t--unit"></a>innerOperation: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja $V $ jest sprzężona.



## <a name="output--t--unit"></a>Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Nowa operacja, której akcja jest reprezentowana przez jednostkę $U ^ {\dagger} V U $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementu docelowego, na którym działa każda z wewnętrznych i zewnętrznych operacji.

## <a name="remarks"></a>Uwagi

Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ConjugatedByA](xref:Microsoft.Quantum.Canon.ConjugatedByA)
- [Microsoft. Quantum. Canon. ConjugatedByC](xref:Microsoft.Quantum.Canon.ConjugatedByC)
- [Microsoft. Quantum. Canon. ConjugatedByCA](xref:Microsoft.Quantum.Canon.ConjugatedByCA)
- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)