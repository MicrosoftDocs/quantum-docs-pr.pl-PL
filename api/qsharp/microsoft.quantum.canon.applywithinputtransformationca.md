---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207789"
---
# <a name="applywithinputtransformationca-operation"></a>ApplyWithInputTransformationCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


W przypadku operacji, która akceptuje pewne dane wejściowe, funkcja zwracająca dane wyjściowe zgodne z tą operacją oraz dane wejściowe do tej funkcji, stosuje operację przy użyciu funkcji, aby przekształcić dane wejściowe na formularz oczekiwany przez operację.

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="fn--u---t"></a>fn: "U-> t

Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.


### <a name="op--t--unit--is-adj--ctl"></a>op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Operacja, która ma zostać zastosowana.


### <a name="input--u"></a>dane wejściowe: ' U

Wejście do funkcji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


### <a name="u"></a>' U



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyWithInputTransformation](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationC](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)