---
uid: Microsoft.Quantum.Diagnostics.DumpRegister
title: DumpRegister, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpRegister
qsharp.summary: Dumps the current target machine's status associated with the given qubits.
ms.openlocfilehash: a6d29dbf0525077fd804563f85f189740fdc0429
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712838"
---
# <a name="dumpregister-function"></a>DumpRegister, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package [](https://nuget.org/packages/)


Zrzuca stan bieżącej maszyny docelowej skojarzony z danym qubits.

```qsharp
function DumpRegister<'T> (location : 'T, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="location--t"></a>Lokalizacja: 'T

Zawiera informacje o tym, gdzie wygenerować zrzut stanu.


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Lista qubits do raportowania.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

Brak.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Ta metoda umożliwia zrzut informacji skojarzonych ze stanem danego qubits do pliku lub innej lokalizacji.
Rzeczywiste wygenerowane informacje i semantyka `location` są specyficzne dla każdej maszyny docelowej. Jednak podanie pustej krotki jako lokalizacji ( `()` ) zazwyczaj oznacza wygenerowanie danych wyjściowych w konsoli programu.

W przypadku lokalnego symulatora pełnego stanu dystrybuowanego w ramach zestawu Quantum Development Kit ta metoda oczekuje ciągu z ścieżką do pliku, w którym będzie zapisywać stan danego qubits (tj. funkcja Wave odpowiedniego podsystemu) jako Jednowymiarowa tablica liczb zespolonych, w których każdy element reprezentuje amplitudę prawdopodobieństwa pomiaru odpowiedniego stanu.
Jeśli dany qubits są Entangled z innymi qubit i ich stan nie może zostać oddzielony, tylko zgłasza, że qubits są Entangled.