---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716025"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operację dla każdego indeksu w Kartezjańskiegoej liczbie całkowitej.

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Opis

Iteracyjnie stosuje operację dla każdego elementu Kartezjańskiegoego zakresu `0..(bound - 1)` .

## <a name="input"></a>Dane wejściowe

### <a name="power--int"></a>potęga: [int](xref:microsoft.quantum.lang-ref.int)

Kartezjańskiego, do którego `0..(bound - 1)` ma zostać zgłoszony zakres.


### <a name="bound--int"></a>powiązane: [int](xref:microsoft.quantum.lang-ref.int)

Specyfikacja zakresu, który ma być powtarzany, wyrażony jako długość zakresu.


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać wywołana dla każdego elementu w danej kartezjańskiego.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)