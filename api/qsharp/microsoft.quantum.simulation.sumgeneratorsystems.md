---
uid: Microsoft.Quantum.Simulation.SumGeneratorSystems
title: SumGeneratorSystems, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: SumGeneratorSystems
qsharp.summary: Adds multiple `GeneratorSystem`s to create a new GeneratorSystem.
ms.openlocfilehash: b667a6af313b5bb8950a34a6d0406976bde49311
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719880"
---
# <a name="sumgeneratorsystems-function"></a>SumGeneratorSystems, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Dodaje wiele `GeneratorSystem` s do utworzenia nowego GeneratorSystem.

```qsharp
function SumGeneratorSystems (generatorSystems : Microsoft.Quantum.Simulation.GeneratorSystem[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Dane wejściowe

### <a name="generatorsystems--generatorsystem"></a>generatorSystems: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)[]

Tablica typu `GeneratorSystem[]` .



## <a name="output--generatorsystem"></a>Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Reprezentuje system, który jest sumą systemów generatora danych wejściowych.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Symulacja. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)