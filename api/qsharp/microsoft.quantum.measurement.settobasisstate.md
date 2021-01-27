---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: dfa054360a5e82b7ae6ec5a6d52e7d5fe566f42e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854628"
---
# <a name="settobasisstate-operation"></a>SetToBasisState, operacja

Przestrzeń nazw: [Microsoft. Quantum. Pomiar](xref:Microsoft.Quantum.Measurement)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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