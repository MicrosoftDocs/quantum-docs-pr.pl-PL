---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 5bbc8d6113fb36bfd4050b98538bb61bbac02185
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720213"
---
# <a name="paulicoefficientfromgenidx-function"></a>PauliCoefficientFromGenIdx, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Wyodrębnia współczynnik terminu Pauli opisanego przez `GeneratorIndex` .

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="generatorindex--generatorindex"></a>generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

`GeneratorIndex` Typ, który koduje termin Pauli.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Współczynnik terminu opisanego przez `GeneratorIndex` .