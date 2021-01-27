---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: a75d46ef0b38fbcef99b7ab22454e1b5a9475b11
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837773"
---
# <a name="jordanwignergeneratorsystem-function"></a>JordanWignerGeneratorSystem, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Konwertuje hamiltonian opisane przez `JWOptimizedHTerms` do, `GeneratorSystem` wyrażone w zakresie `GeneratorIndex` Konwencji zdefiniowanej w tym pliku.

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Dane wejściowe

### <a name="data--jwoptimizedhterms"></a>dane: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

Opis elementu hamiltonian w `JWOptimizedHTerms` formacie.



## <a name="output--generatorsystem"></a>Wynik: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Reprezentacja hamiltonian jako `GeneratorSystem` .