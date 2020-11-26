---
uid: Microsoft.Quantum.Canon.Bound
title: Bound — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207602"
---
# <a name="bound-function"></a>Bound — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Dane wejściowe

### <a name="operations--t--unit-"></a>operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)> []

Sekwencja operacji do wykonania na danym wejściu.



## <a name="output--t--unit"></a>Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym każda z operacji w tablicy działa.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. Quantum. Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)