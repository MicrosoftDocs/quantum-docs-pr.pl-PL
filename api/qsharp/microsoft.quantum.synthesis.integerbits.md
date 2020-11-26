---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: d6566716f5a63c090668d9582b7b000c16d1f6a5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231096"
---
# <a name="integerbits-function"></a>IntegerBits, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca wszystkie pozycje, w których są ustawiane bity liczby całkowitej.

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a>Dane wejściowe

### <a name="value--int"></a>wartość: [int](xref:microsoft.quantum.lang-ref.int)

Liczba nieujemna.


### <a name="length--int"></a>Długość: [int](xref:microsoft.quantum.lang-ref.int)

Liczba bitów w rozszerzeniu binarnym `value` .



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica zawierająca wszystkie pozycje bitowe (rozpoczynając od 0), które są 1 w rozszerzeniu binarnym, `value` biorąc pod uwagę wszystkie bity do położenia `length - 1` .  Wszystkie pozycje są uporządkowane w tablicy według położenia w kolejności rosnącej.