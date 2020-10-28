---
uid: Microsoft.Quantum.Diagnostics.DumpMachine
title: DumpMachine, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpMachine
qsharp.summary: Dumps the current target machine's status.
ms.openlocfilehash: c85cf6764bdc913a71448c525318f45743bf1df0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712875"
---
# <a name="dumpmachine-function"></a>DumpMachine, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


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