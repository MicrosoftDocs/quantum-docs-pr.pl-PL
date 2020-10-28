---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkcja zgięcia
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719208"
---
# <a name="fold-function"></a>Funkcja zgięcia

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Iteruje funkcję `f` za pomocą tablicy `array` , zwracając `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Dane wejściowe

### <a name="folder--statet---state"></a>folder: ("State, t) — stan >"

Funkcja, która ma być składana na tablicy.


### <a name="state--state"></a>stan: "stan

Początkowy stan folderu.


### <a name="array--t"></a>Tablica: t []

Tablica wartości do przejęcia.



## <a name="output--state"></a>Wynik: "stan

Końcowy stan zwrócony przez folder po przeprowadzeniu iteracji dla wszystkich elementów `array` .

## <a name="type-parameters"></a>Parametry typu

### <a name="state"></a>"Stan

Typ Stanów `folder` , w których działa funkcja, tj., akceptuje jako pierwszy argument i zwraca.
### <a name="t"></a>'C

Typ `array` elementów.