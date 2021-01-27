---
uid: Microsoft.Quantum.Math.PlusA
title: Plusa — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PlusA
qsharp.summary: Returns the sum (concatenation) of two inputs.
ms.openlocfilehash: 14e9bfdbe4b70b4730e5bfc64a0ee81ab3cecaaf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842715"
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