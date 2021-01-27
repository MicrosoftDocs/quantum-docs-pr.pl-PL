---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: feb5da771ee6cb6a750fa76f9ffd8f5a3e0b5734
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840049"
---
# <a name="uncurriedopa-function"></a>UncurriedOpA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.
Modyfikator `A` wskazuje, że operacje są sąsiadujące.

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="curriedop--t---u--unit--is-adj"></a>curriedOp: > ' U => [jednostką](xref:microsoft.quantum.lang-ref.unit)  jest przymiotnik

Funkcja zwracająca operacje.



## <a name="output--tu--unit--is-adj"></a>Wynik: (t, ' U) => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą

Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego argumentu funkcji rozwinięte.
### <a name="u"></a>' U

Typ drugiego argumentu funkcji rozwinięte.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)