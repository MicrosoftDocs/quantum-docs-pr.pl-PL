---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851762"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Konwertuje hamiltonian w `HTerm[]` formacie danych na GeneratorSystem.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Dane wejściowe

### <a name="data--hterm"></a>dane: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Dane wejściowe w `HTerm[]` formacie.


### <a name="termtype--int"></a>termtype: [int](xref:microsoft.quantum.lang-ref.int)[]

Dodatkowe informacje dodane do GeneratorIndex.



## <a name="output--generatorsystem"></a>Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

GeneratorSystem reprezentujący hamiltonian reprezentowane przez dane wejściowe `data` .