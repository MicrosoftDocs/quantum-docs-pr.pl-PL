---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717635"
---
# <a name="applyseriesofopsca-operation"></a>ApplySeriesOfOpsCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy. (Sąsiadujące + kontrolowane)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="listofops--t--unit-adj--ctl"></a>listOfOps: t [] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL []

Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana. Są one stosowane sekwencyjnie, najpierw najniższy indeks.
Każdy z nich musi mieć zarówno sąsiadujące, jak i kontrolowane Funktor.


### <a name="targets--int"></a>elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []

Zagnieżdżone tablice opisujące cele operacji. Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.


### <a name="register--t"></a>Rejestr: t []

Zarejestruj się, aby zarejestrować się w qubit.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)