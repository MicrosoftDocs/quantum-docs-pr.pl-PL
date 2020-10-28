---
uid: Microsoft.Quantum.Arrays.Transposed
title: Transponowano funkcję
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718812"
---
# <a name="transposed-function"></a>Transponowano funkcję

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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