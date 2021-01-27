---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846253"
---
# <a name="columnat-function"></a>ColumnAt, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wyodrębnia kolumnę z macierzy.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Opis

Ta funkcja wyodrębnia kolumnę w macierzy w kolejności wierszy.
Wyodrębnienie wiersza corrsponds do dostępu do elementu pierwszego indeksu i w związku z tym nie wymaga dalszej obróbki.

## <a name="input"></a>Dane wejściowe

### <a name="column--int"></a>kolumna: [int](xref:microsoft.quantum.lang-ref.int)

Kolumna macierzy


### <a name="matrix--t"></a>Macierz: t [] []

Macierz 2-wymiarową w kolejności wierszy



## <a name="output--t"></a>Wynik: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `matrix` .

## <a name="example"></a>Przykład

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. transponowanych](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. ukośny](xref:Microsoft.Quantum.Arrays.Diagonal)