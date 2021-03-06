---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkcja ukośna
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 2857046f59a958fed106af0944b75baaa3292e96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842826"
---
# <a name="diagonal-function"></a>Funkcja ukośna

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca tablicę elementów ukośnych macierzy 2-wymiarowej.

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Opis

Jeśli Dwuwymiarowa tablica nie ma kształtu kwadratowego, zostanie zwrócony ukośnie na minimum względem liczby wierszy i kolumn.

## <a name="input"></a>Dane wejściowe

### <a name="matrix--t"></a>Macierz: t [] []

Macierz 2-wymiarową w kolejności wierszy



## <a name="output--t"></a>Wynik: t []



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ każdego elementu `matrix` .

## <a name="example"></a>Przykład

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let diagonal = Diagonal(matrix);
// same as: column = [1, 5, 9]
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. transponowanych](xref:Microsoft.Quantum.Arrays.Transposed)