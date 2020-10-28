---
uid: Microsoft.Quantum.Canon.DelayCA
title: DelayCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayCA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4b4be55436d6619511a12c6fb7fbd0f23989152a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716268"
---
# <a name="delayca-operation"></a>DelayCA, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje daną operację z opóźnieniem.

```qsharp
operation DelayCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a>Opis

Mając daną operację i dane wejściowe dla tej operacji, stosuje operację po udostępnieniu dodatkowych danych wejściowych.
W szczególności wyrażenie `Delay(op, arg, _)` jest operacją, która stosuje się `op` do `arg` momentu wywołania.
Wyrażenie `Delay(op,arg,_)` umożliwia opóźnienie aplikacji `op` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-ctl--adj"></a>op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Operacja, która ma zostać zastosowana.


### <a name="arg--t"></a>ARG: 'T

Dane wejściowe, do których zostanie zastosowana operacja.


### <a name="aux--unit"></a>AUX: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

Argument używany do opóźniania stosowania operacji przy użyciu częściowej aplikacji.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać opóźniona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delayed)