---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Podzielona funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845541"
---
# <a name="partitioned-function"></a>Podzielona funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Dzieli tablicę na wiele części.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Dane wejściowe

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)[]

Liczba elementów w każdej części tablicy


### <a name="arr--t"></a>ARR: t []

Tablica wejściowa do podzielenia.



## <a name="output--t"></a>Wynik: t [] []

Wiele tablic, w których pierwsza jest pierwsza tablica `nElements[0]` `arr` i druga tablica jest następną `nElements[1]` z `arr` itd. Ostatnia tablica będzie zawierać wszystkie pozostałe elementy.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="example"></a>Przykład

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```