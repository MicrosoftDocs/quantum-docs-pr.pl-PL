---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207466"
---
# <a name="composedoutput-function"></a>ComposedOutput, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca dane wyjściowe kompozycji `inner` i `outer` dla danego danych wejściowych.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Dane wejściowe

### <a name="outer--u---v"></a>zewnętrzne: "U->" V




### <a name="inner--t---u"></a>wewnętrzny: brak > ' U




### <a name="target--t"></a>element docelowy: 'T





## <a name="output--v"></a>Wynik: ' V



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


### <a name="u"></a>' U


### <a name="v"></a>"V

