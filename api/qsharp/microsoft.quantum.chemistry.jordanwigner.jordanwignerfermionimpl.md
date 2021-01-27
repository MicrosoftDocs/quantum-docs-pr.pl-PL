---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionImpl
title: JordanWignerFermionImpl, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5b975457803b8978d846bcd3c8256dfacdb90bee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98838181"
---
# <a name="jordanwignerfermionimpl-operation"></a>JordanWignerFermionImpl, operacja

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Reprezentuje Generator dynamiczny jako zestaw bram, które są symulowane i rozszerzanie w JordanWigner.

Zobacz [dynamiczne modelowanie generatora](../libraries/data-structures#dynamical-generator-modeling) , aby uzyskać więcej szczegółów.

```qsharp
operation JordanWignerFermionImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Indeks generatora, który ma być reprezentowany jako ewolucja jednostkowa w JordanWigner.


### <a name="stepsize--double"></a>stepSize: [Double](xref:microsoft.quantum.lang-ref.double)

Mnożnik dotyczący czasu trwania ewolucji przez termin przywoływany w `generatorIndex` .


### <a name="qubits--qubit"></a>qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Zarejestruj działania podejmowane przez operator zmiany czasu.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

