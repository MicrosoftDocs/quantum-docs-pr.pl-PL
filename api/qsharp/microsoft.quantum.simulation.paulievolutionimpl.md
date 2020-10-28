---
uid: Microsoft.Quantum.Simulation.PauliEvolutionImpl
title: PauliEvolutionImpl, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliEvolutionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the Pauli basis.

  See [Dynamical Generator Modeling](/quantum/libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 2fc9fda2dd6eec71d8b17ba8a00d8545e517eec8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720204"
---
# <a name="paulievolutionimpl-operation"></a>PauliEvolutionImpl, operacja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w Pauli.

Zobacz [dynamiczne modelowanie generatora](/quantum/libraries/data-structures#dynamical-generator-modeling) , aby uzyskać więcej szczegółów.

```qsharp
operation PauliEvolutionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, delta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa na podstawie Pauli.


### <a name="delta--double"></a>Delta: [Double](xref:microsoft.quantum.lang-ref.double)

Mnożnik dotyczący czasu trwania ewolucji przez termin przywoływany w `generatorIndex` .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zarejestruj działania podejmowane przez operator zmiany czasu.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

