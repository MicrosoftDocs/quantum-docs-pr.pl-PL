---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715218"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.
Modyfikator `A` wskazuje, że operacje są sąsiadujące.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="curriedop--t---u--unit-adj"></a>curriedOp: > ' U => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Funkcja zwracająca operacje.



## <a name="output--tu--unit-adj"></a>Wynik: (t, ' U) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego argumentu funkcji rozwinięte.
### <a name="u"></a>' U

Typ drugiego argumentu funkcji rozwinięte.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)