---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848003"
---
# <a name="pauliblockencoding-function"></a>PauliBlockEncoding, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tworzy moduł kodowania bloku dla hamiltonian.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ jest opisywany przez sumę Pauliych warunków $P _j $, każdy z rzeczywistym czynnikiem $ \ alpha_j $.

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Dane wejściowe

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` , który opisuje $H $ jako sumę Pauli warunków



## <a name="output--doubleblockencodingreflection"></a>Dane wyjściowe: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Pierwszy parametr

Jedna z norm współczynników $ \Alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Drugi parametr

`BlockEncodingReflection`Jednostkowa $U $ Hamiltonian $H $. Ponieważ ta jednostka jest taka sama jak $U ^ 2 = I $, jest również odbiciem.

## <a name="remarks"></a>Uwagi

Jest on uzyskiwany przez przygotowanie i cofnięcie przygotowania stanu $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ i skonstruowanie kontrolowanego jednostkowo jednostki <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> i <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .