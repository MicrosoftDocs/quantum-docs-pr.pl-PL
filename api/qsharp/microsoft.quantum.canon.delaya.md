---
uid: Microsoft.Quantum.Canon.DelayA
title: Opóźnienie operacji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207143"
---
# <a name="delaya-operation"></a>Opóźnienie operacji

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje daną operację z opóźnieniem.

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a>Opis

Mając daną operację i dane wejściowe dla tej operacji, stosuje operację po udostępnieniu dodatkowych danych wejściowych.
W szczególności wyrażenie `Delay(op, arg, _)` jest operacją, która stosuje się `op` do `arg` momentu wywołania.
Wyrażenie `Delay(op,arg,_)` umożliwia opóźnienie aplikacji `op` .

## <a name="input"></a>Dane wejściowe

### <a name="op--t--unit--is-adj"></a>op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą

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