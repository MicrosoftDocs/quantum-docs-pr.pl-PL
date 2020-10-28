---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716669"
---
# <a name="boundc-function"></a>BoundC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.
Modyfikator `C` wskazuje, że wszystkie operacje w tablicy są kontrolowane.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="operations--t--unit-ctl"></a>operacje: 'T =>a lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) []

Sekwencja operacji do wykonania na danym wejściu.



## <a name="output--t--unit-ctl"></a>Dane wyjściowe: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym każda z operacji w tablicy działa.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)