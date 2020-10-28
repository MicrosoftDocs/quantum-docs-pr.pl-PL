---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724224"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="e8b65-102">StateOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="e8b65-102">StateOracle user defined type</span></span>

<span data-ttu-id="e8b65-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e8b65-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e8b65-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8b65-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8b65-105">Przedstawia oprogramowanie Oracle do przygotowywania stanu.</span><span class="sxs-lookup"><span data-stu-id="e8b65-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="e8b65-106">Dane wejściowe programu Oracle $O $ to:</span><span class="sxs-lookup"><span data-stu-id="e8b65-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="e8b65-107">Liczba całkowita indeksowania flagi qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="e8b65-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="e8b65-108">Rejestr systemu $s $, który będzie przechowywać żądany stan Quantum $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="e8b65-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="e8b65-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e8b65-109">Remarks</span></span>

<span data-ttu-id="e8b65-110">Ta Oracle zdefiniowana przez $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ działa w ramach obliczania stanu podstawy $ \ket {0} \_ {f} \ket {0} \_ s $, aby utworzyć stan docelowy $ \ket{\psi} \_ s $ z amplitudą $ \lambda $ na podstawie oflagowanej przez $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="e8b65-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="e8b65-111">Pierwszy parametr jest indeksem do rejestru qubit $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="e8b65-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="e8b65-112">Drugi parametr obejmował oba rejestry.</span><span class="sxs-lookup"><span data-stu-id="e8b65-112">The second parameter encompassed both registers.</span></span>