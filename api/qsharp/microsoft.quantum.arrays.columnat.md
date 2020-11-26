---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210103"
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

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. transponowanych](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. ukośny](xref:Microsoft.Quantum.Arrays.Diagonal)