---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 6f8f80aacd3386ba61675101acb87e09fff5afff
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193934"
---
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="59285-102">DeterministicStateOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="59285-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="59285-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="59285-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="59285-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59285-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59285-105">Reprezentuje niedeterministyczną przygotowanie stanu.</span><span class="sxs-lookup"><span data-stu-id="59285-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="59285-106">Dane wejściowe dla programu Oracle $O $ to:</span><span class="sxs-lookup"><span data-stu-id="59285-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="59285-107">Rejestr, w którym będzie przechowywany żądany stan Quantum $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="59285-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="59285-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="59285-108">Remarks</span></span>

<span data-ttu-id="59285-109">Ta Oracle zdefiniowana przez $O \ket {0} = \ket{\psi} $ działa na stanie bazowym obliczeń $ \ket $, {0} Aby utworzyć stan $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="59285-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="59285-110">Pierwszy parametr jest rejestrem qubit $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="59285-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>