---
uid: Microsoft.Quantum.Canon.ApplyWithA
title: ApplyWithA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithA
qsharp.summary: Given two operations, applies one as conjugated with the other.
ms.openlocfilehash: f1ff31da53952931426d358cbedad44a50d87f5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716926"
---
# <a name="applywitha-operation"></a>ApplyWithA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dwie operacje mają zastosowanie jeden, jak jest sprzężony z drugim.

```qsharp
operation ApplyWithA<'T> (outerOperation : ('T => Unit is Adj), innerOperation : ('T => Unit is Adj), target : 'T) : Unit
```


## <a name="description"></a>Opis

Dwie operacje opisane odpowiednio przez operatory jednostkowe $U $ i $V $, stosują je w sekwencji $U ^ {\dagger} V U $. Oznacza to, że ta operacja implementuje operator jednostki dostarczone przez $V $ sprzężone z $U $.

## <a name="input"></a>Dane wejściowe

### <a name="outeroperation--t--unit-adj"></a>outerOperation: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja $U $, która powinna być używana do sprzężonia $V $. Należy zauważyć, że operacja zewnętrzna $U $ musi być przylegające, ale nie musi być sterowana.


### <a name="inneroperation--t--unit-adj"></a>innerOperation: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja $V $ jest sprzężona.


### <a name="target--t"></a>element docelowy: 'T

Dane wejściowe, które mają zostać przekazane do operacji zewnętrznych i wewnętrznych.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym działa każda z operacji wewnętrznych i zewnętrznych.

## <a name="remarks"></a>Uwagi

Operacja zewnętrzna jest zawsze zakładana jako przyleganie, ale nie musi być sterowana, aby można było sterować połączonymi operacjami.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyWith](xref:Microsoft.Quantum.Canon.ApplyWith)
- [Microsoft. Quantum. Canon. ApplyWithC](xref:Microsoft.Quantum.Canon.ApplyWithC)
- [Microsoft. Quantum. Canon. ApplyWithCA](xref:Microsoft.Quantum.Canon.ApplyWithCA)