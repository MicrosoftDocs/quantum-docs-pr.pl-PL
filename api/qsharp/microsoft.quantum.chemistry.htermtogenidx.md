---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: 59391a882fdbc55172ee93a7428c1735bbb29500
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216034"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Konwertuje termin hamiltonian w `HTerm` formacie danych na GeneratorIndex.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Dane wejściowe

### <a name="term--hterm"></a>termin: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

Dane wejściowe w `HTerm` formacie.


### <a name="termtype--int"></a>termtype: [int](xref:microsoft.quantum.lang-ref.int)[]

Dodatkowe informacje dodane do GeneratorIndex.



## <a name="output--generatorindex"></a>Wynik: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

GeneratorIndex reprezentujący termin hamiltonian reprezentowany przez `term` , wraz z dodatkowymi informacjami dodanymi przez `termType` .