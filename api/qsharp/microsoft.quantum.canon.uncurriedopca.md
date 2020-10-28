---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715204"
---
# <a name="uncurriedopca-function"></a>UncurriedOpCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.
Modyfikator `CA` wskazuje, że operacje są kontrolowane i sąsiadujące.

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="curriedop--t---u--unit-ctl--adj"></a>curriedOp: t-> ' U => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Funkcja zwracająca operacje.



## <a name="output--tu--unit-ctl--adj"></a>Dane wyjściowe: (t, ' U) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego argumentu funkcji rozwinięte.
### <a name="u"></a>' U

Typ drugiego argumentu funkcji rozwinięte.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)