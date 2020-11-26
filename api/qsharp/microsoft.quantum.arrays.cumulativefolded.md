---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: ffb934d06f6be06cbc35a523c90d2c54e0a51353
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210033"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Łączy zamapowane i zgięcie w jedną funkcję

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Opis

Ta funkcja iteruje `fn` funkcję za pośrednictwem tablicy, rozpoczynając od początkowego stanu `state` i zwraca wszystkie wartości pośrednie, bez uwzględniania stanu początkowego.

## <a name="input"></a>Dane wejściowe

### <a name="fn--statet---state"></a>fn: ("stan, t) — stan >"

Funkcja, która ma być składana nad tablicą


### <a name="state--state"></a>stan: "stan

Początkowy stan, który ma zostać złożony


### <a name="array--t"></a>Tablica: t []

Tablica wartości, które mają zostać złożone



## <a name="output--state"></a>Dane wyjściowe: "State []

Wszystkie Stany pośrednie, w tym stan końcowy, ale nie stan początkowy.
Długość tablicy wyjściowej jest taka sama jak długość `array` .

## <a name="type-parameters"></a>Parametry typu

### <a name="state"></a>"Stan

Typ Stanów, w których `fn` działa funkcja, tj., akceptuje jako pierwsze dane wejściowe i zwraca.
### <a name="t"></a>'C

Typ `array` elementów.