---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842254"
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