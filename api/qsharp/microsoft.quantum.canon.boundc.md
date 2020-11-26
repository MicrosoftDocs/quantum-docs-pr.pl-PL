---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207585"
---
# <a name="boundc-function"></a>BoundC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.
Modyfikator `C` wskazuje, że wszystkie operacje w tablicy są kontrolowane.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="operations--t--unit--is-ctl"></a>operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL []

Sekwencja operacji do wykonania na danym wejściu.



## <a name="output--t--unit--is-ctl"></a>Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL

Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym każda z operacji w tablicy działa.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)