---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: ApplyIfElseRA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: d0181d98a9867f71d8a8f8dea4331e5a13f9e59c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718144"
---
# <a name="applyifelsera-operation"></a>ApplyIfElseRA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje jeden z dwóch operacji sąsiednich, w zależności od wartości klasycznego wyniku.

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit
```


## <a name="description"></a>Opis

W związku z `result` tym, stosuje operację `zeroOp` za pomocą `zeroInput` jako dane wejściowe `result` , gdy jest równe `Zero` , i ma zastosowanie, `oneOp(oneInput)` gdy `result == One` .

## <a name="input"></a>Dane wejściowe

### <a name="result--__invalidresult__"></a>wynik: __nieprawidłowe <Result>__

Wynik pomiaru służący do określenia `zeroOp` , czy lub `oneOp` ma zostać zastosowany.


### <a name="zeroop--t--unit-adj"></a>zeroOp: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja sąsiedniego, która ma zostać zastosowana w przypadku `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: 'T

Dane wejściowe, które mają być dostarczone przez `zeroOp` `result == Zero` .


### <a name="oneop--u--unit-adj"></a>oneOp: ' U => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja sąsiedniego, która ma zostać zastosowana w przypadku `result == One` .


### <a name="oneinput--u"></a>oneInput: ' U

Dane wejściowe, które mają być dostarczone przez `oneOp` `result == One` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, `zeroOp` która ma być stosowana warunkowo.
### <a name="u"></a>' U

Typ wejściowy operacji, `oneOp` która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)