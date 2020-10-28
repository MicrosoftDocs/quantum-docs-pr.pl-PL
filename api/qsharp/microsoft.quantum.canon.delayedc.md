---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 7cfd77b0bb2d91c5a1c4bb5bc84e052421d733a9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716212"
---
# <a name="delayedc-function"></a>DelayedC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Zwraca operację, która stosuje daną operację z danym argumentem.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit-ctl"></a>op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)

Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej


### <a name="arg--t"></a>ARG: 'T

Dane wejściowe, do których `op` zostanie zastosowana operacja.



## <a name="output--unit--unit-ctl"></a>Dane wyjściowe [Unit](xref:microsoft.quantum.lang-ref.unit) : => lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) jednostki

Nowa operacja stosowana `op` z danymi wejściowymi `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać opóźniona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)