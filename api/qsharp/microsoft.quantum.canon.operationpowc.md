---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715689"
---
# <a name="operationpowc-function"></a>OperationPowC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Wywołuje operację do potęgi.
Modyfikator `C` wskazuje, że operacja jest sterowana.

Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-ctl"></a>op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja $U $ reprezentująca bramę do powtórzenia.


### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)

Liczba powtórzeń $U $.



## <a name="output--t--unit-ctl"></a>Dane wyjściowe: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ operacji, która ma być włączona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)