---
uid: Microsoft.Quantum.Simulation.MultiplyGeneratorSystem
title: MultiplyGeneratorSystem, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: MultiplyGeneratorSystem
qsharp.summary: Multiplies the coefficient of all terms in a `GeneratorSystem`.
ms.openlocfilehash: 1d28de99dab3f7aca4bf3706fe98f5ef7c5286a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720237"
---
# <a name="multiplygeneratorsystem-function"></a>MultiplyGeneratorSystem, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Mnoży współczynnik wszystkich warunków w `GeneratorSystem` .

```qsharp
function MultiplyGeneratorSystem (multiplier : Double, generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Dane wejściowe

### <a name="multiplier--double"></a>mnożnik: [Double](xref:microsoft.quantum.lang-ref.double)

Mnożnik na współczynniku.


### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Do pomnożenia.



## <a name="output--generatorsystem"></a>Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

`GeneratorSystem`Reprezentuje system z współczynnikiem większego współczynnika `multiplier` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Symulacja. GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)