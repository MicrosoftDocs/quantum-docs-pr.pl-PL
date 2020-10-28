---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724541"
---
# <a name="identitygeneratorindex-function"></a>IdentityGeneratorIndex, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Zwraca indeks generatora spójny z zerem hamiltonian, `H = 0` który odnosi się do operacji ewolucji tożsamości.

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Dane wejściowe

### <a name="idxterm--int"></a>idxTerm: [int](xref:microsoft.quantum.lang-ref.int)

To dane wejściowe są ignorowane i zdefiniowane dla spójności z <xref:microsoft.quantum.simulation.generatorsystem> typem zdefiniowanym przez użytkownika.



## <a name="output--generatorindex"></a>Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Indeks generatora reprezentujący ewolucję w hamiltonian $H = $0.