---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216629"
---
# <a name="curriedop-function"></a>CurriedOp, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wersję rozwinięte operacji dla dwóch danych wejściowych.

Oznacza to, że w wyniku operacji z dwoma danymi wejściowymi ta funkcja stosuje curry isomorphism $f (x, y) \equiv f (x) (y) $, aby zwrócić operację jednego danych wejściowych, która zwraca operację jednego danych wejściowych.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Dane wejściowe

### <a name="op--tu--unit"></a>op: (t, ' U) = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, której dane wejściowe to para.



## <a name="output--t---u--unit"></a>Wynik: brak > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit) 

Operacja, która akceptuje pierwszy element pary i zwraca operację, która akceptuje jako dane wejściowe drugiego elementu danych wejściowych pierwotnej operacji.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego składnika funkcji zdefiniowanej w parach.
### <a name="u"></a>' U

Typ drugiego składnika funkcji zdefiniowanej w parach.

## <a name="remarks"></a>Uwagi

Następujące elementy są równoważne:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```