---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponowano funkcję
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850934"
---
# <a name="transposed-function"></a>Transponowano funkcję

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca transpozycję macierzy reprezentowanej jako tablica tablic.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Opis

Dane wejściowe jako $r \times c $ z $r $ wierszy i $c $ Columns.  Macierz jest oparta na wierszach, tj., `matrix[i][j]` uzyskuje dostęp do elementu w wierszu $i $ i column $j $.

Ta funkcja zwraca $c \times r $ Matrix, która jest transponowaną macierzy wejściowej.

## <a name="input"></a>Dane wejściowe

### <a name="matrix--t"></a>Macierz: t [] []

Oparta na wierszach $r \times c $ Matrix



## <a name="output--t"></a>Wynik: t [] []

Transponowano $c \times r $ Matrix

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `matrix` .

## <a name="example"></a>Przykład

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```