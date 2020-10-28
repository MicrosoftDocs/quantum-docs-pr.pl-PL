---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: ApplyControlledOnInt, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718353"
---
# <a name="applycontrolledonint-operation"></a>ApplyControlledOnInt, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package [](https://nuget.org/packages/)


Stosuje operacje jednostkowe w rejestrze docelowym, jeśli stan rejestru kontroli odpowiada określonej dodatniej liczbie całkowitej.

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="numberstate--int"></a>numberState: [int](xref:microsoft.quantum.lang-ref.int)

Nieujemna liczba całkowita, w której `oracle` powinna być kontrolowana operacja.


### <a name="oracle--t--unit-adj--ctl"></a>Oracle: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja jednostkowa, która ma być kontrolowana.


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr Quantum kontrolujący aplikację `oracle` .


### <a name="targetregister--t"></a>targetRegister: 'T

Rejestr, który ma zostać zastosowany `oracle` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

Wartość `numberState` jest interpretowana przy użyciu kodowania little-endian.

`numberState` musi mieć co najwyżej $2 ^ \texttt{Length (controlRegister)}-$1.
Na przykład `numberState = 537` oznacza, że `oracle` jest stosowana, jeśli `controlRegister` jest w stanie $ \ket {537} $.