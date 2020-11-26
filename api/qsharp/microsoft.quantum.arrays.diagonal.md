---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Funkcja ukośna
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221542"
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

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Arrays. transponowanych](xref:Microsoft.Quantum.Arrays.Transposed)