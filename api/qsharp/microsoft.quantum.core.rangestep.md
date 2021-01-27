---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853599"
---
# <a name="rangestep-function"></a>RangeStep, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca liczbę całkowitą określającą sposób obliczania następnej wartości zakresu.

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="range--range"></a>zakres: [zakres](xref:microsoft.quantum.lang-ref.range)





## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Zdefiniowana wartość kroku danego zakresu.

## <a name="remarks"></a>Uwagi

Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .