---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709753"
---
# <a name="inputencoder-function"></a>InputEncoder, funkcja

Przestrzeń nazw: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Package [](https://nuget.org/packages/)


Biorąc pod sobą zestaw współczynników i tolerancję, zwraca operację przygotowania stanu, która przygotowuje każdy współczynnik jako odpowiadającą amplitudę podstawy obliczeniowej.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Dane wejściowe

### <a name="coefficients--double"></a>współczynniki: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)[]

Współczynniki do zakodowania w stanie wejściowym.



## <a name="output--stategenerator"></a>Wynik: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Operacja przygotowania stanu, która przygotowuje dane współczynniki jako stan wejścia dla danego rejestru.