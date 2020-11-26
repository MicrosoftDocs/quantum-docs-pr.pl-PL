---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funkcja _IdentityTimeDependentGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225605"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>Funkcja _IdentityTimeDependentGeneratorSystem

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zwraca System generatora spójny z hamiltonian `H(s) = 0` , gdzie `s` jest parametrem harmonogramu.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Dane wejściowe

### <a name="schedule--double"></a>Harmonogram: [Double](xref:microsoft.quantum.lang-ref.double)

To dane wejściowe są ignorowane i zdefiniowane dla spójności z <xref:microsoft.quantum.canon.timedependentgeneratorsystem> typem zdefiniowanym przez użytkownika.



## <a name="output--generatorsystem"></a>Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

System generatora reprezentujący ewolucję w hamiltonian $H (s) = $0 dla wszystkich $s $.