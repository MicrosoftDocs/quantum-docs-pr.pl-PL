---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 005d7862214abb3dcb9c0caa006343720d179a52
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854464"
---
# <a name="stateoracle-user-defined-type"></a><span data-ttu-id="ed2fc-102">StateOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="ed2fc-102">StateOracle user defined type</span></span>

<span data-ttu-id="ed2fc-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="ed2fc-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="ed2fc-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ed2fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ed2fc-105">Przedstawia oprogramowanie Oracle do przygotowywania stanu.</span><span class="sxs-lookup"><span data-stu-id="ed2fc-105">Represents an oracle for state preparation.</span></span>

<span data-ttu-id="ed2fc-106">Dane wejściowe programu Oracle $O $ to:</span><span class="sxs-lookup"><span data-stu-id="ed2fc-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="ed2fc-107">Liczba całkowita indeksowania flagi qubit $f $.</span><span class="sxs-lookup"><span data-stu-id="ed2fc-107">An integer indexing the flag qubit $f$.</span></span>
- <span data-ttu-id="ed2fc-108">Rejestr systemu $s $, który będzie przechowywać żądany stan Quantum $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="ed2fc-108">The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.</span></span>

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="ed2fc-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ed2fc-109">Remarks</span></span>

<span data-ttu-id="ed2fc-110">Ta Oracle zdefiniowana przez $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, $ $ działa w ramach obliczania stanu podstawy $ \ket {0} \_ {f} \ket {0} \_ s $, aby utworzyć stan docelowy $ \ket{\psi} \_ s $ z amplitudą $ \lambda $ na podstawie oflagowanej przez $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="ed2fc-110">This oracle defined by $$ O\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, $$ acts on the on computational basis state $\ket{0}\_{f}\ket{0}\_s$ to create the target state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{1}\_f$.</span></span>
<span data-ttu-id="ed2fc-111">Pierwszy parametr jest indeksem do rejestru qubit $ \ket {0} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="ed2fc-111">The first parameter is an index to the qubit register of $\ket{0}\_f$.</span></span> <span data-ttu-id="ed2fc-112">Drugi parametr obejmował oba rejestry.</span><span class="sxs-lookup"><span data-stu-id="ed2fc-112">The second parameter encompassed both registers.</span></span>