---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846249"
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

## <a name="example"></a>Przykład

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```