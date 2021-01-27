---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840293"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Przykład

Po danej operacji `op` następujące dwa fragmenty kodu są równoważne:

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)