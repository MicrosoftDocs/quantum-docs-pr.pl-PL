---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6b2cf09c23942a586414daccb99cbb27b5026b9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226608"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Przedstawia oprogramowanie Oracle do przygotowywania stanu.

Dane wejściowe programu Oracle $O $ to:

- Liczba całkowita indeksowania flagi qubit $f $.
- Rejestr systemu $s $, który będzie przechowywać żądany stan Quantum $ \ket{\psi} \_ s $.

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Uwagi

Ta Oracle zdefiniowana przez $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ działa w ramach obliczania stanu podstawy $ \ket {0} \_ {f} \ket {0} \_ s $, aby utworzyć stan docelowy $ \ket{\psi} \_ s $ z amplitudą $ \lambda $ na podstawie oflagowanej przez $ \ket {1} \_ f $.
Pierwszy parametr jest indeksem do rejestru qubit $ \ket {0} \_ f $. Drugi parametr obejmował oba rejestry.