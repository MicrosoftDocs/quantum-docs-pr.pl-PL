---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: 579300d4efb9e22cb671fbb4bce0a6f72dd0e2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853418"
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