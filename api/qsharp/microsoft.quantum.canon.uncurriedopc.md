---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 05df99dce8b167f32078ce256748647ceb94d0fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851993"
---
# <a name="uncurriedopc-function"></a>UncurriedOpC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.
Modyfikator `C` wskazuje, że operacje są kontrolowane.

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="curriedop--t---u--unit--is-ctl"></a>curriedOp: > ' U => [jednostką](xref:microsoft.quantum.lang-ref.unit)  CTL

Funkcja zwracająca operacje.



## <a name="output--tu--unit--is-ctl"></a>Wynik: (t, ' U) = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL

Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego argumentu funkcji rozwinięte.
### <a name="u"></a>' U

Typ drugiego argumentu funkcji rozwinięte.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. UncurriedOp](xref:Microsoft.Quantum.Canon.UncurriedOp)