---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831115"
---
# <a name="rangestart-function"></a>RangeStart, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca zdefiniowaną wartość początkową danego zakresu.

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="range--range"></a>zakres: [zakres](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Zdefiniowana wartość początkowa danego zakresu.

## <a name="remarks"></a>Uwagi

Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .

Należy zauważyć, że zdefiniowana wartość początkowa zakresu jest taka sama jak pierwszy element sekwencji, chyba że zakres określa pustą sekwencję (na przykład 2.. 1).