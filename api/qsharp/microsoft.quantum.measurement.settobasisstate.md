---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724672"
---
# <a name="settobasisstate-operation"></a>SetToBasisState, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Package [](https://nuget.org/packages/)


Ustawia qubit do danego stanu podstaw obliczeniowych przez zmierzenie qubit i zastosowanie bitowego przerzucania w razie potrzeby.

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="desired--__invalidresult__"></a>pożądane __: <Result> nieprawidłowe__

Stan bazowy, do którego należy ustawić qubit.


### <a name="target--qubit"></a>obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, którego stan ma być ustawiony.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Jako niezmienna tej operacji wywoływanie `M(q)` natychmiast po `SetToBasisState(result, q)` powrocie zostanie zwrócone `result` .