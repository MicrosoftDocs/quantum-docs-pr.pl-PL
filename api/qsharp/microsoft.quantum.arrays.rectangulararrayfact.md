---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845502"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje warunek, którego Dwuwymiarowa tablica ma kształt prostokątny

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Opis

Ta funkcja potwierdza, że każdy wiersz w tablicy ma tę samą długość.

## <a name="input"></a>Dane wejściowe

### <a name="array--t"></a>Tablica: t [] []

Dwuwymiarowa tablica elementów


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Komunikat do wydrukowania, jeśli tablica nie jest tablicą prostokątną



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `array` .

## <a name="example"></a>Przykład

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. SquareArrayFact](xref:Microsoft.Quantum.Arrays.SquareArrayFact)