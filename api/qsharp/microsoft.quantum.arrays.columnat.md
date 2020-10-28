---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719457"
---
# <a name="columnat-function"></a>ColumnAt, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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