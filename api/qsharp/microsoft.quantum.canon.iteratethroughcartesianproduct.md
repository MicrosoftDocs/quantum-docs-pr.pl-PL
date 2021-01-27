---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: a0aaa8ef6aa6798d31c810254c92820f8136800c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840277"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje operację dla każdego indeksu w kartezjańskiego produktu kilku zakresów.

```qsharp
operation IterateThroughCartesianProduct (bounds : Int[], op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>Opis

Iteracyjnie stosuje operację dla każdego elementu kartezjańskiego produktu `0..(bounds[0] - 1)` ,,... `0..(bounds[1] - 1)` , `0..(bounds[Length(bounds) - 1] - 1)`

## <a name="input"></a>Dane wejściowe

### <a name="bounds--int"></a>granice: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica określająca zakresy, które mają być powtarzane, z każdym zakresem określanym jako długość całkowita.


### <a name="op--int--unit"></a>op: [int](xref:microsoft.quantum.lang-ref.int)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)> 

Operacja, która ma zostać wywołana dla każdego elementu danego produktu kartezjańskiego.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Przykład

Po danej operacji `op` następujące dwa fragmenty kodu są równoważne:

```qsharp
IterateThroughCartesianProduct([3, 4, 5], op);
```

```qsharp
op([0, 0, 0]);
op([1, 0, 0]);
op([2, 0, 0]);
op([0, 1, 0]);
// ...
op([0, 3, 0]);
op([0, 0, 1]);
//
op([2, 3, 4]);
```

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)