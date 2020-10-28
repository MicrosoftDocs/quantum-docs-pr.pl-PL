---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715213"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.
Modyfikator `C` wskazuje, że operacje są kontrolowane.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="curriedop--t---u--unit-ctl"></a>curriedOp: t-> ' U => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Funkcja zwracająca operacje.



## <a name="output--tu--unit-ctl"></a>Dane wyjściowe: (t, ' U) => CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)

Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego argumentu funkcji rozwinięte.
### <a name="u"></a>' U

Typ drugiego argumentu funkcji rozwinięte.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)