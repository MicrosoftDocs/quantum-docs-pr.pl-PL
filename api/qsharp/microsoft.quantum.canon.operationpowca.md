---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715675"
---
# <a name="operationpowca-function"></a>OperationPowCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Wywołuje operację do potęgi.
Modyfikator `A` wskazuje, że operacja jest sterowana i sąsiadująca.

Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-ctl--adj"></a>op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Operacja $U $ reprezentująca bramę do powtórzenia.


### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)

Liczba powtórzeń $U $.



## <a name="output--t--unit-ctl--adj"></a>Dane wyjściowe: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + korekta

Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ operacji, która ma być włączona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)