---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: e7eb2dfce060b61e27deae31e3c1fc6dc3d7655c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202111"
---
# <a name="dumpmachine-function"></a>DumpMachine, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zrzuca stan bieżącej maszyny docelowej.

```qsharp
function DumpMachine<'T> (location : 'T) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="location--t"></a>Lokalizacja: 'T

Zawiera informacje o tym, gdzie wygenerować zrzut maszyny.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

Brak.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Ta metoda umożliwia zrzut informacji o bieżącym stanie maszyny docelowej do pliku lub innej lokalizacji.
Rzeczywiste wygenerowane informacje i semantyka `location` są specyficzne dla każdej maszyny docelowej. Jednak podanie pustej krotki jako lokalizacji ( `()` ) lub po prostu pominięcie `location` parametru zazwyczaj oznacza wygenerowanie danych wyjściowych w konsoli.

W przypadku lokalnego symulatora pełnego stanu dystrybuowanego w ramach zestawu Quantum Development Kit ta metoda oczekuje ciągu z ścieżką do pliku, w którym pisze funkcję Wave jako jednowymiarową tablicę liczb zespolonych, w której każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru odpowiedniego stanu.