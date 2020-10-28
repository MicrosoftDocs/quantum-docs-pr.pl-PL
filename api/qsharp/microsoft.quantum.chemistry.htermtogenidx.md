---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714835"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia](xref:Microsoft.Quantum.Chemistry)

Package [](https://nuget.org/packages/)


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