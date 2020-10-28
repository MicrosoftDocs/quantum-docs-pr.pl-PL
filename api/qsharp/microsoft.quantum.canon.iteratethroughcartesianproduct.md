---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianProduct
title: IterateThroughCartesianProduct, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianProduct
qsharp.summary: Applies an operation for each index in the Cartesian product of several ranges.
ms.openlocfilehash: e4fc71f6f707639f6f89eece8546ec2fb434a15a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716039"
---
# <a name="iteratethroughcartesianproduct-operation"></a>IterateThroughCartesianProduct, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


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



## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. IterateThroughCartesianPower](xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower)