---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: ApplyWithInputTransformationC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716842"
---
# <a name="applywithinputtransformationc-operation"></a>ApplyWithInputTransformationC, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


W przypadku operacji, która akceptuje pewne dane wejściowe, funkcja zwracająca dane wyjściowe zgodne z tą operacją oraz dane wejściowe do tej funkcji, stosuje operację przy użyciu funkcji, aby przekształcić dane wejściowe na formularz oczekiwany przez operację.

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="fn--u---t"></a>fn: "U-> t

Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.


### <a name="op--t--unit-ctl"></a>op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)

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
- [Microsoft. Quantum. Canon. ApplyWithInputTransformationCA](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [Microsoft. Quantum. Canon. TransformedOperation](xref:Microsoft.Quantum.Canon.TransformedOperation)