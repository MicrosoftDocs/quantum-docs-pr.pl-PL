---
uid: Microsoft.Quantum.Arrays.Sorted
title: Funkcja posortowana
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: cb8a1ef438d798c8201ed9f52677e253770df1d3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845444"
---
# <a name="sorted-function"></a>Funkcja posortowana

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dana tablica zwraca elementy tej tablicy posortowane według danej funkcji porównywania.

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>Dane wejściowe

### <a name="comparison--tt---bool"></a>Porównanie: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funkcja, która porównuje dwa elementy, które `a` są uważane za mniej niż lub równą `b` if `comparison(a, b)` `true` .


### <a name="array--t"></a>Tablica: t []

Tablica, która ma zostać posortowana.



## <a name="output--t"></a>Wynik: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `array` .

## <a name="example"></a>Przykład

Poniższy fragment kodu Sortuje tablicę liczb całkowitych, która występuje w kolejności rosnącej:

```qsharp
let sortedArray = Sorted(LessThanOrEqualI, [3, 17, 11, -201, -11]);
```

## <a name="remarks"></a>Uwagi

Przyjmuje się `comparison` , że funkcja jest przechodnia, na przykład jeśli `comparison(a, b)` i `comparison(b, c)` , `comparison(a, c)` jest przyjmowana. Jeśli ta właściwość nie jest wstrzymana, dane wyjściowe tej funkcji mogą być nieprawidłowe.

Ponieważ jest to funkcja, wyniki są całkowicie determinstic, nawet jeśli dwa elementy są uważane za równe `comparison` . to jest, kiedy `comparison(a, b)` i `comparison(b, a)` są oba `true` .
W szczególności sortowanie wykonywane przez tę funkcję jest gwarantowane jako stabilne, więc jeśli dwa elementy `a` i `b` występują w tej kolejności w `array` i są uznawane za równe w `comparison` , a następnie `a` pojawią się przed `b` w danych wyjściowych.

Na przykład:

```qsharp
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```