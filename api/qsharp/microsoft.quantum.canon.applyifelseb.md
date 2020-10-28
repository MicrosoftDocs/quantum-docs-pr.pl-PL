---
uid: Microsoft.Quantum.Canon.ApplyIfElseB
title: ApplyIfElseB, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseB
qsharp.summary: Applies one of two operations, depending on the value of a classical bit.
ms.openlocfilehash: 68c06a5141b9ff423c2d18adc3a9e162eed939f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718221"
---
# <a name="applyifelseb-operation"></a>ApplyIfElseB, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje jedną z dwóch operacji, w zależności od wartości klasycznego bitu.

```qsharp
operation ApplyIfElseB<'T, 'U> (bit : Bool, (trueOp : ('T => Unit), trueInput : 'T), (falseOp : ('U => Unit), falseInput : 'U)) : Unit
```


## <a name="description"></a>Opis

Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .

## <a name="input"></a>Dane wejściowe

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.


### <a name="trueop--t--unit"></a>trueOp: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać zastosowana, gdy `bit` ma wartość `true` .


### <a name="trueinput--t"></a>trueInput: 'T

Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .


### <a name="falseop--u--unit"></a>falseOp: ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać zastosowana, gdy `bit` ma wartość `false` .


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