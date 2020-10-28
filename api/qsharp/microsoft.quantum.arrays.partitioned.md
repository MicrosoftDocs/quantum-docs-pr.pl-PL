---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Podzielona funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718977"
---
# <a name="partitioned-function"></a>Podzielona funkcja

Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package [](https://nuget.org/packages/)


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

