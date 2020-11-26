---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207262"
---
# <a name="controlledonint-function"></a>ControlledOnInt, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca operator jednostki, który stosuje platformę Oracle w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej dodatniej liczbie całkowitej.

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Dodatnia liczba całkowita.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL

Operator jednostkowy.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[], t) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Operator jednostkowy stosowany `oracle` w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada stanowi liczby `numberState` .

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Wartość `numberState` jest interpretowana przy użyciu kodowania little-endian.