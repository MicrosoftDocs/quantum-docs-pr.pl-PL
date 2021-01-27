---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855400"
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

## <a name="example"></a>Przykład

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```