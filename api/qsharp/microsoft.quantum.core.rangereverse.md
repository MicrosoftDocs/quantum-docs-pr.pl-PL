---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713230"
---
# <a name="rangereverse-function"></a>RangeReverse, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package [](https://nuget.org/packages/)


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