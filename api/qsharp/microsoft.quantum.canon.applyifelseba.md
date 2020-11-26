---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: 74d43344481c5a808e84ce9c9e36fa3e83cd0d89
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218669"
---
# <a name="applyifelseba-operation"></a>ApplyIfElseBA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje jedną z dwóch operacji przylegających, w zależności od wartości klasycznego bitu.

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a>Opis

Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .

## <a name="input"></a>Dane wejściowe

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.


### <a name="trueop--t--unit--is-adj"></a>trueOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja przylegania, która ma zostać zastosowana, gdy `bit` ma wartość `true` .


### <a name="trueinput--t"></a>trueInput: 'T

Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .


### <a name="falseop--u--unit--is-adj"></a>falseOp: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

Operacja przylegania, która ma zostać zastosowana, gdy `bit` ma wartość `false` .


### <a name="falseinput--u"></a>falseInput: ' U

Dane wejściowe, które mają być dostarczone, `falseOp` gdy `bit` ma wartość `false` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, `trueOp` która ma być stosowana warunkowo.
### <a name="u"></a>' U

Typ wejściowy operacji, `falseOp` która ma być stosowana warunkowo.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyIfZero](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [Microsoft. Quantum. Canon. ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [Microsoft. Quantum. Canon. ApplyIfElseRC](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [Microsoft. Quantum. Canon. ApplyIfElseRA](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [Microsoft. Quantum. Canon. ApplyIfElseRCA](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)