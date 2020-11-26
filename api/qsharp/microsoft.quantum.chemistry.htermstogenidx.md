---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: dbe0718fa3b5439a2987d455fdad73731c988678
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216017"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Konwertuje indeks na termin hamiltonian w `HTerm[]` formacie danych na GeneratorIndex.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Dane wejściowe

### <a name="data--hterm"></a>dane: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Dane wejściowe w `HTerm[]` formacie.


### <a name="termtype--int"></a>termtype: [int](xref:microsoft.quantum.lang-ref.int)[]

Dodatkowe informacje dodane do GeneratorIndex.


### <a name="idx--int"></a>IDX: [int](xref:microsoft.quantum.lang-ref.int)

Indeks do terminu hamiltonian



## <a name="output--generatorindex"></a>Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

GeneratorIndex reprezentujący termin hamiltonian reprezentowany przez `data[idx]` , wraz z dodatkowymi informacjami dodanymi przez `termType` .