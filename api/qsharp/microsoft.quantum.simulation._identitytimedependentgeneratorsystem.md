---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funkcja _IdentityTimeDependentGeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 960842f50353c01362f90eb38d979fb7c4f15d9a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857981"
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