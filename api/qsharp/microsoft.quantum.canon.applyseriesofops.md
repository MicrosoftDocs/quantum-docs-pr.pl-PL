---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717668"
---
# <a name="applyseriesofops-operation"></a>ApplySeriesOfOps, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy.

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="listofops--t--unit-"></a>listOfOps: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit)> []

Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana. Są one stosowane sekwencyjnie, najpierw najniższy indeks.


### <a name="targets--int"></a>elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []

Zagnieżdżone tablice opisujące cele operacji. Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.


### <a name="register--t"></a>Rejestr: t []

Zarejestruj się, aby zarejestrować się w qubit.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)