---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853662"
---
# <a name="rangereverse-function"></a>RangeReverse, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca nowy zakres, który jest odwrotnością zakresu wejściowego.

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a>Dane wejściowe

### <a name="r--range"></a>r: [zakres](xref:microsoft.quantum.lang-ref.range)

Zakres wejściowy.



## <a name="output--range"></a>Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)

Nowy zakres, który jest odwrotny od danego zakresu.

## <a name="remarks"></a>Uwagi

Należy zauważyć, że odwrócenie zakresu nie jest po prostu `end` .. `-step` .. `start` , ponieważ rzeczywisty ostatni element zakresu nie może być taki sam jak `end` .