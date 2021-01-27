---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: GetQubitsAvailableToUse, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827803"
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