---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 6904054bb1aff3a57c80882694b4c217812b2b81
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842238"
---
# <a name="intstopaulis-function"></a>IntsToPaulis, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konwertuje tablicę liczb całkowitych na tablicę operatorów Pauli pojedynczej qubit.

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>Dane wejściowe

### <a name="ints--int"></a>liczby całkowite: [int](xref:microsoft.quantum.lang-ref.int)[]

Tablica liczb całkowitych w zakresie, `0..3`  który ma zostać przekonwertowany na operatory Pauli.



## <a name="output--pauli"></a>Wynik: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tablica `paulis` operatorów Pauli o takiej `Pauli[]` samej długości jak `ints` taka, która `paulis[idxPauli]` jest równa elementowi `[PauliI, PauliX, PauliY, PauliZ]` danego elementu `ints[idxPauli]` .