---
uid: Microsoft.Quantum.Arrays.IsSorted
title: Funkcja IsSorted
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220839"
---
# <a name="issorted-function"></a>Funkcja IsSorted

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica zwraca czy tablica jest sortowana zgodnie z definicją przez daną funkcję porównania.

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Dane wejściowe

### <a name="comparison--tt---bool"></a>Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja, która porównuje dwa elementy, które `a` są uważane za mniej niż lub równą `b` if `comparison(a, b)` `true` .


### <a name="array--t"></a>Tablica: t []

Tablica, która ma zostać sprawdzona.



## <a name="output--bool"></a>Wynik: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Jeśli i tylko wtedy, gdy dla każdej pary `a` elementów `b` i `array` występuje w tej kolejności, `comparison(a, b)` jest `true` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `array` .

## <a name="remarks"></a>Uwagi

Przyjmuje się `comparison` , że funkcja jest przechodnia, na przykład jeśli `comparison(a, b)` i `comparison(b, c)` , `comparison(a, c)` jest przyjmowana. Jeśli ta właściwość nie jest wstrzymana, dane wyjściowe tej funkcji mogą być nieprawidłowe.