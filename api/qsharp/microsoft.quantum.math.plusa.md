---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 0c6fdcf7c59dc5d89bf83e285339046b5ad5a57e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709604"
---
# <a name="plusa-function"></a>Plusa — funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Package [](https://nuget.org/packages/)


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