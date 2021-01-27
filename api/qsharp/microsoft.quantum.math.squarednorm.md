---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848215"
---
# <a name="squarednorm-function"></a>SquaredNorm, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca kwadratową 2-normatywną wartość wektora.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Opis

Zwraca kwadratową 2-normę wektora; oznacza to, że dane wejściowe $ \vec{x} $ zwracają wartość $ \ sum_i x_i ^ 2 $.

## <a name="input"></a>Dane wejściowe

### <a name="array--double"></a>Array: [Double](xref:microsoft.quantum.lang-ref.double)[]

Wektor, którego wartość jest równa 2, która ma zostać zwrócona.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Kwadratowa 2-norma `array` .