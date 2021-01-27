---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 9a1f6189428b086c38b1d0f289afb18c2cf1be40
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850866"
---
# <a name="applyseriesofopsca-operation"></a>ApplySeriesOfOpsCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje listę operacji Ops i ich obiekty docelowe sekwencyjnie na tablicy. (Sąsiadujące + kontrolowane)

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="listofops--t--unit--is-adj--ctl"></a>listOfOps: t [] = [jednostka](xref:microsoft.quantum.lang-ref.unit) > to przymiotnik + CTL []

Lista operacji, z których każda pobiera tablicę, która ma zostać zastosowana. Są one stosowane sekwencyjnie, najpierw najniższy indeks.
Każdy z nich musi mieć zarówno sąsiadujące, jak i kontrolowane Funktor.


### <a name="targets--int"></a>elementy docelowe: [int](xref:microsoft.quantum.lang-ref.int)[] []

Zagnieżdżone tablice opisujące cele operacji. Każda tablica powinna zawierać listę liczby całkowite opisujących indeksy, które mają być używane.


### <a name="register--t"></a>Rejestr: t []

Zarejestruj się, aby zarejestrować się w qubit.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="example"></a>Przykład

Poniżej zawarto następujące zastosowania: EXP ([PauliX, PauliY], 0,5) do qubits 0, 1//then X do qubit 2 Let Ops = [EXP ([PauliX, PauliY], 0,5, _), ApplyToFirstQubitCA (X, _)]; Zezwól na indeksy = [[0, 1], [2]]; ApplySeriesOfOpsCA (Ops, indeksy, qubitArray);

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)