---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: f02267d48cf42fb5b02782dc6b667ac7b60a05dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724294"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Package [](https://nuget.org/packages/)


Reprezentuje niedeterministyczną przygotowanie stanu.

Dane wejściowe dla programu Oracle $O $ to:

- Rejestr, w którym będzie przechowywany żądany stan Quantum $ \ket{\psi} \_ s $.

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Uwagi

Ta Oracle zdefiniowana przez $O \ket {0} = \ket{\psi} $ działa na stanie bazowym obliczeń $ \ket $, {0} Aby utworzyć stan $ \ket{\psi} $.
Pierwszy parametr jest rejestrem qubit $ \ket{\psi} $.