---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713160"
---
# <a name="rangestep-function"></a>RangeStep, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)

Package [](https://nuget.org/packages/)


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