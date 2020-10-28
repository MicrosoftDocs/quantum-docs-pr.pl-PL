---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716632"
---
# <a name="boundca-function"></a>BoundCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.
Modyfikator `CA` wskazuje, że wszystkie operacje w tablicy są sąsiadujące i kontrolowane.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="operations--t--unit-adj--ctl"></a>operacje: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL []

Sekwencja operacji do wykonania na danym wejściu.



## <a name="output--t--unit-adj--ctl"></a>Wynik: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym każda z operacji w tablicy działa.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)