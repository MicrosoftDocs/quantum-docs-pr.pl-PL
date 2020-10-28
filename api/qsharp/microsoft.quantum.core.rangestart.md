---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713169"
---
# <a name="rangestart-function"></a>RangeStart, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package [](https://nuget.org/packages/)


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