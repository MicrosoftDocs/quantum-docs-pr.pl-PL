---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721727"
---
# <a name="targetstatereflectionoracle-function"></a>TargetStateReflectionOracle, funkcja

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package [](https://nuget.org/packages/)


Konstruuje `ReflectionOracle` Informacje o stanie docelowym jednoznacznie oznaczone przez flagę qubit.

Stan docelowy ma jeden qubit ustawiony na 1, a wszystkie pozostałe 0: $ \ket {1} _F $.

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>Dane wejściowe

### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Indeks do flagi qubit $f $ z programu Oracle.



## <a name="output--reflectionoracle"></a>Wynik: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

`ReflectionOracle`Odzwierciedla informacje o stanie oznaczonym przez $ \ket {1} _F $.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)