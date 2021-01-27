---
uid: Microsoft.Quantum.Canon.ApplyIfElseBC
title: ApplyIfElseBC, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical bit.
ms.openlocfilehash: 6140a8382cbd00589d1aef99e004f71f5d9295a9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841816"
---
# <a name="applyifelsebc-operation"></a>ApplyIfElseBC, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje jedną z dwóch operacji kontrolowanych, w zależności od wartości klasycznej.

```qsharp
operation ApplyIfElseBC<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Ctl), trueInput : 'T), (falseOp : ('U => Unit is Ctl), falseInput : 'U)) : Unit is Ctl
```


## <a name="description"></a>Opis

Na przykład bit `bit` , stosuje operację `trueOp` wraz z `trueInput` jako dane wejściowe `bit` , gdy jest i ma `true` zastosowanie, `falseOp(falseInput)` gdy `bit` jest `false` .

## <a name="input"></a>Dane wejściowe

### <a name="bit--bool"></a>bit: [bool](xref:microsoft.quantum.lang-ref.bool)

Wartość logiczna służąca do określenia `trueOp` , czy `falseOp` ma zostać zastosowana.


### <a name="trueop--t--unit--is-ctl"></a>trueOp: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL

Operacja umożliwiająca przeprowadzenie kontroli, która ma być stosowana, gdy `bit` jest `true` .


### <a name="trueinput--t"></a>trueInput: 'T

Dane wejściowe, które mają być dostarczone, `trueOp` gdy `bit` ma wartość `true` .


### <a name="falseop--u--unit--is-ctl"></a>falseOp: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL

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