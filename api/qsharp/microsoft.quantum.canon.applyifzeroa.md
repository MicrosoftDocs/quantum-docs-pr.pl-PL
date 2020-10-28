---
uid: Microsoft.Quantum.Canon.ApplyIfZeroA
title: ApplyIfZeroA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being zero.
ms.openlocfilehash: d324cd970e8df49ceb51b6bf5c9f3c9c3ff142f9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718055"
---
# <a name="applyifzeroa-operation"></a>ApplyIfZeroA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację przylegającej do wartości wynikowej dla klasycznego wyniku równego zero.

```qsharp
operation ApplyIfZeroA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a>Opis

Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `Zero` . Jeśli `One` nie, nic się nie dzieje z `target` .
Sufiks `A` wskazuje, że operacja, która ma zostać zastosowana, to przylegający.

## <a name="input"></a>Dane wejściowe

### <a name="result--__invalidresult__"></a>wynik: __nieprawidłowe <Result>__

Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.


### <a name="op--t--unit-adj"></a>op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja, która ma być stosowana warunkowo.


### <a name="target--t"></a>element docelowy: 'T

Dane wejściowe, do których zostanie zastosowana operacja.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyIfZeroC](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [Microsoft. Quantum. Canon. ApplyIfZeroA](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [Microsoft. Quantum. Canon. ApplyIfZeroCA](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)