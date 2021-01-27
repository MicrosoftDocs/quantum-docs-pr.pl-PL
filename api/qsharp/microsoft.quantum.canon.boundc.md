---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841044"
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

## <a name="example"></a>Przykład

Następujące elementy są równoważne:

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

oraz

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)