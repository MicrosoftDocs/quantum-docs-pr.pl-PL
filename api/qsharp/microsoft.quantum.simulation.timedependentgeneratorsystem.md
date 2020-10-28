---
uid: Microsoft.Quantum.Simulation.TimeDependentGeneratorSystem
title: TimeDependentGeneratorSystem typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentGeneratorSystem
qsharp.summary: Represents a time-dependent dynamical generator as a function from time to the value of the dynamical generator at that time.
ms.openlocfilehash: 144a44448c9fda7a038b17ac7c49f63e8cc4dd55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719877"
---
# <a name="timedependentgeneratorsystem-user-defined-type"></a>TimeDependentGeneratorSystem typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Reprezentuje Generator dynamiczny zależny od czasu do wartości generatora dynamicznego w tym czasie.

```qsharp

newtype TimeDependentGeneratorSystem = ((Double -> Microsoft.Quantum.Simulation.GeneratorSystem));
```

