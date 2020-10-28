---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 032d92484dc96481cb981d9d8acfeed248a9116d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718212"
---
# <a name="applyifelsebc-operation"></a>ApplyIfElseBC, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje jedną z dwóch operacji kontrolowanych, w zależności od wartości klasycznej.

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a>Opis

Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .

## <a name="input"></a>Dane wejściowe

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.


### <a name="trueop--t--unit-ctl"></a>trueOp: t => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana, gdy `bit` jest `true` .


### <a name="trueinput--t"></a>trueInput: 'T

Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .


### <a name="falseop--u--unit-ctl"></a>falseOp: ' U => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL

Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana, gdy `bit` jest `false` .


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