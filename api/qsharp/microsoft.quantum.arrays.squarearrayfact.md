---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718857"
---
# <a name="squarearrayfact-function"></a>SquareArrayFact, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


Reprezentuje warunek, którego Dwuwymiarowa tablica ma kształt kwadratowy

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>Opis

Ta funkcja potwierdza, że każdy wiersz w tablicy ma tyle elementów jak wiersze (elementy) w tablicy.

## <a name="input"></a>Dane wejściowe

### <a name="array--t"></a>Tablica: t [] []

Dwuwymiarowa tablica elementów


### <a name="message--string"></a>komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)

Komunikat do wydrukowania, jeśli tablica nie jest tablicą kwadratową



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `array` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. RectangularArrayFact](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)