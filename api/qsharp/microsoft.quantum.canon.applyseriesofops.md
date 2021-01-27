---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841495"
---
# <a name="applyseriesofops-operation"></a>ApplySeriesOfOps, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Przykład

Poniżej zawarto następujące zastosowania: EXP ([PauliX, PauliY], 0,5) do qubits 0, 1//then X do qubit 2 Let Ops = [EXP ([PauliX, PauliY], 0,5, _), ApplyToFirstQubit (X, _)]; Zezwól na indeksy = [[0, 1], [2]]; ApplySeriesOfOps (Ops, indeksy, qubitArray);

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)