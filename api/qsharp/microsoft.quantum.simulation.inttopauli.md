---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724849"
---
# <a name="inttopauli-function"></a>IntToPauli, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Konwertuje liczbę całkowitą na operator qubit Pauli.

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>Dane wejściowe

### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Liczba całkowita z zakresu `0..3` do przekonwertowania na operatory Pauli.



## <a name="output--pauli"></a>Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`Operator określony przez `[PauliI, PauliX, PauliY, PauliZ][idx]` .