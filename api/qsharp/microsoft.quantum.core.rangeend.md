---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713244"
---
# <a name="rangeend-function"></a>RangeEnd, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package [](https://nuget.org/packages/)


Zwraca zdefiniowaną wartość końcową danego zakresu, która nie musi być ostatnim elementem w sekwencji.

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="range--range"></a>zakres: [zakres](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Zdefiniowana wartość końcowa danego zakresu.

## <a name="remarks"></a>Uwagi

Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .

Należy zauważyć, że zdefiniowana wartość końcowa zakresu może różnić się od ostatniego elementu w sekwencji określonej przez zakres; na przykład, w zakresie 0.. 2.. 5 ostatni element to 4, ale wartość końcowa to 5.