---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funkcja _IdentityTimeDependentGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710691"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>Funkcja _IdentityTimeDependentGeneratorSystem

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Zwraca System generatora spójny z hamiltonian `H(s) = 0` , gdzie `s` jest parametrem harmonogramu.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Dane wejściowe

### <a name="schedule--double"></a>Harmonogram: [Double](xref:microsoft.quantum.lang-ref.double)

To dane wejściowe są ignorowane i zdefiniowane dla spójności z <xref:microsoft.quantum.canon.timedependentgeneratorsystem> typem zdefiniowanym przez użytkownika.



## <a name="output--generatorsystem"></a>Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

System generatora reprezentujący ewolucję w hamiltonian $H (s) = $0 dla wszystkich $s $.