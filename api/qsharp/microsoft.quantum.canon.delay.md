---
uid: Microsoft.Quantum.Canon.Delay
title: Opóźnienie operacji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716319"
---
# <a name="delay-operation"></a>Opóźnienie operacji

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje daną operację z opóźnieniem.

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a>Opis

Mając daną operację i dane wejściowe dla tej operacji, stosuje operację po udostępnieniu dodatkowych danych wejściowych.
W szczególności wyrażenie `Delay(op, arg, _)` jest operacją, która stosuje się `op` do `arg` momentu wywołania.
Wyrażenie `Delay(op,arg,_)` umożliwia opóźnienie aplikacji `op` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--u"></a>op: 'T => ' U 

Operacja, która ma zostać zastosowana.


### <a name="arg--t"></a>ARG: 'T

Dane wejściowe, do których zostanie zastosowana operacja.


### <a name="aux--unit"></a>AUX: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

Argument używany do opóźniania stosowania operacji przy użyciu częściowej aplikacji.



## <a name="output--u"></a>Wynik: ' U



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C

Typ wejściowy operacji, która ma zostać opóźniona.
### <a name="u"></a>' U

Zwracany typ operacji, która ma zostać opóźniona.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. DelayC](xref:Microsoft.Quantum.Canon.DelayC)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.DelayA)
- [Microsoft. Quantum. Canon. DelayCA](xref:Microsoft.Quantum.Canon.DelayCA)
- [Microsoft. Quantum. Canon. Delay](xref:Microsoft.Quantum.Canon.Delayed)