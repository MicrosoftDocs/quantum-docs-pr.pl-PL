---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: e2b928fa4c9446e16d2bf5e7b68a32d4bba3a528
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717654"
---
# <a name="applyseriesofopsa-operation"></a>ApplySeriesOfOpsA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy. (Sąsiadujący)

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="listofops--t--unit-adj"></a>listOfOps: t [] => korektę [jednostki](xref:microsoft.quantum.lang-ref.unit) []

Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana. Są one stosowane sekwencyjnie, najpierw najniższy indeks.
Każdy element musi mieć przyległych Funktor


### <a name="targets--int"></a>elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []

Zagnieżdżone tablice opisujące cele operacji. Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.


### <a name="register--t"></a>Rejestr: t []

Zarejestruj się, aby zarejestrować się w qubit.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)