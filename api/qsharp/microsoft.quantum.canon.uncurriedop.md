---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715241"
---
# <a name="uncurriedop-function"></a>UncurriedOp, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a>Dane wejściowe

### <a name="curriedop--t---u--unit"></a>curriedOp: t-> ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Funkcja zwracająca operacje.



## <a name="output--tu--unit"></a>Wynik: (t, ' U) = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ pierwszego wejścia do operacji rozwinięte.
### <a name="u"></a>' U

Typ drugiego danych wejściowych do operacji rozwinięte.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. UncurriedOpC](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [Microsoft. Quantum. Canon. UncurriedOpA](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [Microsoft. Quantum. Canon. UncurriedOpCA](xref:Microsoft.Quantum.Canon.UncurriedOpCA)