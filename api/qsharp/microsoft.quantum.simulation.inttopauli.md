---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229209"
---
# <a name="inttopauli-function"></a>IntToPauli, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konwertuje liczbę całkowitą na operator qubit Pauli.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Dane wejściowe

### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita z zakresu `0..3` do przekonwertowania na operatory Pauli.



## <a name="output--pauli"></a>Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Operator określony przez `[PauliI, PauliX, PauliY, PauliZ][idx]` .