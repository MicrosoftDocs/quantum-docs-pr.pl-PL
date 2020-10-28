---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719844"
---
# <a name="integerbits-function"></a>IntegerBits, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Synteza](xref:Microsoft.Quantum.Synthesis)

Package [](https://nuget.org/packages/)


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