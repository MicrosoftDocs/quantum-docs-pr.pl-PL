---
uid: Microsoft.Quantum.Simulation.Unitary
title: Typ zdefiniowany przez użytkownika dla jednostki
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: c34d84fb5f319c285356b284bd1f1c18ec64ef46
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192149"
---
# <a name="unitary-user-defined-type"></a>Typ zdefiniowany przez użytkownika dla jednostki

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje ewolucję w ramach operatora jednostkowego.

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

