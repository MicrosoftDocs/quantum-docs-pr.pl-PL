---
uid: Microsoft.Quantum.Arrays.Reversed
title: Odwrócona funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718908"
---
# <a name="reversed-function"></a>Odwrócona funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Utwórz tablicę zawierającą te same elementy co Tablica wejściowa, ale w odwrotnej kolejności.

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="array--t"></a>Tablica: t []

Tablica, której elementy mają być kopiowane w odwrotnej kolejności.



## <a name="output--t"></a>Wynik: t []

Tablica zawierająca elementy `array[Length(array) - 1]` ... `array[0]`.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ elementów tablicy.