---
uid: Microsoft.Quantum.Simulation.Unitary
title: Typ zdefiniowany przez użytkownika dla jednostki
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725330"
---
# <a name="unitary-user-defined-type"></a>Typ zdefiniowany przez użytkownika dla jednostki

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Reprezentuje ewolucję w ramach operatora jednostkowego.

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

