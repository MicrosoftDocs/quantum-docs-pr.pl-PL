---
uid: Microsoft.Quantum.Canon.BoundA
title: Bound — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716688"
---
# <a name="bounda-function"></a>Bound — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.
Modyfikator `A` wskazuje, że wszystkie operacje w tablicy są sąsiadujące.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="operations--t--unit-adj"></a>operacje: t => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) []

Sekwencja operacji do wykonania na danym wejściu.



## <a name="output--t--unit-adj"></a>Wynik: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit)

Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Obiekt docelowy, na którym każda z operacji w tablicy działa.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)