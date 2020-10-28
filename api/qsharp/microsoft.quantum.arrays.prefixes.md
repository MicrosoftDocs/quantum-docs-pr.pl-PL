---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Funkcja prefiksów
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718941"
---
# <a name="prefixes-function"></a>Funkcja prefiksów

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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