---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 874dae2ba5e842066e9c1582af431a73520e4ccd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209540"
---
# <a name="applyifelser-operation"></a>ApplyIfElseR, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje jedną z dwóch operacji, w zależności od wartości klasycznego wyniku.

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a>Opis

W związku z `result` tym, stosuje operację `zeroOp` za pomocą `zeroInput` jako dane wejściowe `result` , gdy jest równe `Zero` , i ma zastosowanie, `oneOp(oneInput)` gdy `result == One` .

## <a name="input"></a>Dane wejściowe

### <a name="result--__invalidresult__"></a>wynik: __nieprawidłowe <Result>__

Wynik pomiaru służący do określenia `zeroOp` , czy lub `oneOp` ma zostać zastosowany.


### <a name="zeroop--t--unit"></a>zeroOp: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać zastosowana w przypadku `result == Zero` .


### <a name="zeroinput--t"></a>zeroInput: 'T

Dane wejściowe, które mają być dostarczone przez `zeroOp` `result == Zero` .


### <a name="oneop--u--unit"></a>oneOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać zastosowana w przypadku `result == One` .


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