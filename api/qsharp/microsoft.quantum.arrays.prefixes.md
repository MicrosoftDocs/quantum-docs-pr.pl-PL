---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funkcja prefiksów
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845511"
---
# <a name="prefixes-function"></a>Funkcja prefiksów

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Podaną tablicę zwraca wszystkie jej prefiksy.

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>Opis

Zwraca tablicę wszystkich prefiksów, rozpoczynając od tablicy, która ma tylko pierwszy element do momentu ukończenia kompletnej tablicy.

## <a name="input"></a>Dane wejściowe

### <a name="array--t"></a>Tablica: t []

Tablica elementów.



## <a name="output--t"></a>Wynik: t [] []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ `array` elementów.

## <a name="example"></a>Przykład

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```