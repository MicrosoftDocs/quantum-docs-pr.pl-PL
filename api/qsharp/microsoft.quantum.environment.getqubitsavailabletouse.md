---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201414"
---
# <a name="getqubitsavailabletouse-operation"></a>GetQubitsAvailableToUse, operacja

Przestrzeń nazw: [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Zwraca liczbę qubits, która jest obecnie dostępna do użycia.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Liczba qubits, które mogą zostać przydzieloną w `using` instrukcji.
Jeśli używana maszyna docelowa nie dostarcza tych informacji, `-1` zostanie zwrócona wartość.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)