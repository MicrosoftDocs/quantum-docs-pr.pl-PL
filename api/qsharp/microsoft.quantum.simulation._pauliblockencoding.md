---
uid: Microsoft.Quantum.Simulation._PauliBlockEncoding
title: Funkcja _PauliBlockEncoding
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: ba30a7e87bd970961dc87f048aa586ff5c512e2a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710663"
---
# <a name="_pauliblockencoding-function"></a>Funkcja _PauliBlockEncoding

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Tworzy moduł kodowania bloku dla hamiltonian.

Hamiltonian $H = \ sum_ {j} \ alpha_j P_j $ jest opisywany przez sumę Pauliych warunków $P _j $, każdy z rzeczywistym czynnikiem $ \ alpha_j $.

```qsharp
function _PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem, statePrepUnitary : (Double[] -> (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)), multiplexer : ((Int, (Int -> (Qubit[] => Unit is Adj + Ctl))) -> ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a>Dane wejściowe

### <a name="generatorsystem--generatorsystem"></a>generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

A `GeneratorSystem` , który opisuje $H $ jako sumę Pauli warunków


### <a name="stateprepunitary--double---littleendian--unit-adj--ctl"></a>statePrepUnitary: [Double](xref:microsoft.quantum.lang-ref.double)[]-> [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL

Operacja jednostkowa $V $, która stosuje $V jednostkowe _j $ kontrolowane w indeksie $ \ket{j} $, przy użyciu funkcji $f: j\rightarrow V_j $.


### <a name="multiplexer--intint---qubit--unit-adj--ctl---littleendianqubit--unit-adj--ctl"></a>multiplekser: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL)-> ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) korekta + CTL





## <a name="output--doubleblockencodingreflection"></a>Dane wyjściowe: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))

## <a name="first-parameter"></a>Pierwszy parametr

Jedna z norm współczynników $ \Alpha = \ sum_ {j} | \ alpha_j | $.

## <a name="second-parameter"></a>Drugi parametr

`BlockEncodingReflection`Jednostkowa $U $ Hamiltonian $U $. Ponieważ ta jednostka jest taka sama jak $U ^ 2 = I $, jest również odbiciem.

## <a name="remarks"></a>Uwagi

Przykładowe operacje przygotowywania i deprzygotowywania stanu $ \ sum_ {j} \sqrt{\ alpha_j/\Alpha}\ket{j} $ i konstruowania jednostek z kontrolą pomnożoną <xref:microsoft.quantum.canon.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .