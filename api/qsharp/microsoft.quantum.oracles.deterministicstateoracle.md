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
# <a name="deterministicstateoracle-user-defined-type"></a><span data-ttu-id="5b35d-102">DeterministicStateOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="5b35d-102">DeterministicStateOracle user defined type</span></span>

<span data-ttu-id="5b35d-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="5b35d-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="5b35d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5b35d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5b35d-105">Reprezentuje niedeterministyczną przygotowanie stanu.</span><span class="sxs-lookup"><span data-stu-id="5b35d-105">Represents an oracle for deterministic state preparation.</span></span>

<span data-ttu-id="5b35d-106">Dane wejściowe dla programu Oracle $O $ to:</span><span class="sxs-lookup"><span data-stu-id="5b35d-106">The input to the oracle $O$ is:</span></span>

- <span data-ttu-id="5b35d-107">Rejestr, w którym będzie przechowywany żądany stan Quantum $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="5b35d-107">The register that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="5b35d-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="5b35d-108">Remarks</span></span>

<span data-ttu-id="5b35d-109">Ta Oracle zdefiniowana przez $O \ket {0} = \ket{\psi} $ działa na stanie bazowym obliczeń $ \ket $, {0} Aby utworzyć stan $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="5b35d-109">This oracle defined by $O\ket{0}=\ket{\psi}$ acts on the on computational basis state $\ket{0}$ to create the state $\ket{\psi}$.</span></span>
<span data-ttu-id="5b35d-110">Pierwszy parametr jest rejestrem qubit $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="5b35d-110">The first parameter is the qubit register of $\ket{\psi}$.</span></span>