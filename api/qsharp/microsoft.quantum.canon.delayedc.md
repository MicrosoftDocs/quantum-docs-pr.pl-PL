---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207019"
---
# <a name="delayedc-function"></a>DelayedC, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca operację, która stosuje daną operację z danym argumentem.

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit--is-ctl"></a>op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL

Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej


### <a name="arg--t"></a>ARG: 'T

Dane wejściowe, do których `op` zostanie zastosowana operacja.



## <a name="output--unit--unit--is-ctl"></a>Wynik: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) jednostki jest listą CTL

Nowa operacja stosowana `op` z danymi wejściowymi `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać opóźniona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delayed)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)