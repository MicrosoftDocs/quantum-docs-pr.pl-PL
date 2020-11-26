---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204066"
---
# <a name="isnotzero-function"></a>IsNotZero, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Sprawdza, czy `Double` liczba nie jest w przybliżeniu równa zero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="number--double"></a>Liczba: [Double](xref:microsoft.quantum.lang-ref.double)

Liczba do sprawdzenia



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

Zwraca wartość true, jeśli `number` ma wartość bezwzględną większą niż `1e-15` .