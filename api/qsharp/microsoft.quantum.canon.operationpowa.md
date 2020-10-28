---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715717"
---
# <a name="operationpowa-function"></a>OperationPowA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Wywołuje operację do potęgi.
Modyfikator `A` wskazuje, że operacja jest sąsiedni.

Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-adj"></a>op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja $U $ reprezentująca bramę do powtórzenia.


### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)

Liczba powtórzeń $U $.



## <a name="output--t--unit-adj"></a>Wynik: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit)

Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ operacji, która ma być włączona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. OperationPow](xref:Microsoft.Quantum.Canon.OperationPow)