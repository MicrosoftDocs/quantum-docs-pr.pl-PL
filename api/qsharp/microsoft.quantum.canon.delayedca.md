---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 8ee55e2ca7ec2cff9618b5dc66e19d88779d39ce
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716221"
---
# <a name="delayedca-function"></a>DelayedCA, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Zwraca operację, która stosuje daną operację z danym argumentem.

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-ctl--adj"></a>op: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik

Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej


### <a name="arg--t"></a>ARG: 'T

Dane wejściowe, do których `op` zostanie zastosowana operacja.



## <a name="output--unit--unit-ctl--adj"></a>Dane wyjściowe [Unit](xref:microsoft.quantum.lang-ref.unit) : => lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) jednostki i korekta

Nowa operacja stosowana `op` z danymi wejściowymi `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać opóźniona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)