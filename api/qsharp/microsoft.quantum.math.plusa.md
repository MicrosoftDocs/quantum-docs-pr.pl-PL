---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: fe19c5d2e075624516376a5d5fa49014acb295ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194835"
---
# <a name="plusa-function"></a>Plusa — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca sumę (konkatenację) dwóch danych wejściowych.

```qsharp
function PlusA<'Element> (a : 'Element[], b : 'Element[]) : 'Element[]
```


## <a name="input"></a>Dane wejściowe

### <a name="a--element"></a>a: "element []

Pierwsze dane wejściowe $a $ mają być sumowane.


### <a name="b--element"></a>b: "element []

Druga wartość wejściowa $b $ do sumowania.



## <a name="output--element"></a>Output: "element []

Suma $a + b $.

## <a name="type-parameters"></a>Parametry typu

### <a name="element"></a>"Element

Typ każdego elementu w każdej z dwóch tablic wejściowych.