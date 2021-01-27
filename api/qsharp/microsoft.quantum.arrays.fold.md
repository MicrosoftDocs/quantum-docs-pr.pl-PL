---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkcja zgięcia
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848605"
---
# <a name="fold-function"></a>Funkcja zgięcia

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>Przykład

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```