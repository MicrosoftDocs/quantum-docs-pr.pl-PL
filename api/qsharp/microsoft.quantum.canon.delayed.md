---
uid: Microsoft.Quantum.Canon.Delayed
title: Funkcja opóźniona
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delayed
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 820a38c2b4de2e0151d55bd88fb4f69567182f6b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716254"
---
# <a name="delayed-function"></a>Funkcja opóźniona

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Zwraca operację, która stosuje daną operację z danym argumentem.

```qsharp
function Delayed<'T, 'U> (op : ('T => 'U), arg : 'T) : (Unit => 'U)
```


## <a name="input"></a>Dane wejściowe

### <a name="op--t--u"></a>op: 'T => ' U 

Operacja, która ma zostać zastosowana.


### <a name="arg--t"></a>ARG: 'T

Dane wejściowe, do których zostanie zastosowana operacja.



## <a name="output--unit--u"></a>Dane wyjściowe: [Unit](xref:microsoft.quantum.lang-ref.unit) => ' U 

Nowa operacja stosowana `op` z danymi wejściowymi `arg`

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać opóźniona.
### <a name="u"></a>' U

Zwracany typ operacji, która ma zostać opóźniona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. DelayedC](xref:Microsoft.Quantum.Canon.DelayedC)
- [Microsoft. Quantum. Canon. opóźnione](xref:Microsoft.Quantum.Canon.DelayedA)
- [Microsoft. Quantum. Canon. DelayedCA](xref:Microsoft.Quantum.Canon.DelayedCA)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delay)