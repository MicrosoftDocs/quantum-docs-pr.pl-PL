---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718060"
---
# <a name="applyifzero-operation"></a>ApplyIfZero, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację warunkową dla klasycznej wartości wynikowej równej zero.

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a>Opis

Dana operacja `op` i wartość wynikowa mają `result` zastosowanie `op` do elementu `target` if `result` is `Zero` . Jeśli `One` nie, nic się nie dzieje z `target` .

## <a name="input"></a>Dane wejściowe

### <a name="result--__invalidresult__"></a>wynik: __nieprawidłowe <Result>__

Wynik pomiaru, który kontroluje, czy operacja jest stosowana, czy nie.


### <a name="op--t--unit"></a>op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

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