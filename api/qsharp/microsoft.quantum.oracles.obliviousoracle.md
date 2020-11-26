---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 2f92dcb28ec669229dfaf9bcb23eef9234552b8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193883"
---
# <a name="obliviousoracle-user-defined-type"></a><span data-ttu-id="84122-102">ObliviousOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="84122-102">ObliviousOracle user defined type</span></span>

<span data-ttu-id="84122-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="84122-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="84122-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84122-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84122-105">Reprezentuje wzmocnienie amplitudy Oracle for Oblivious.</span><span class="sxs-lookup"><span data-stu-id="84122-105">Represents an oracle for oblivious amplitude amplification.</span></span>

<span data-ttu-id="84122-106">Dane wejściowe programu Oracle $O $ to:</span><span class="sxs-lookup"><span data-stu-id="84122-106">The inputs to the oracle $O$ are:</span></span>

- <span data-ttu-id="84122-107">$A rejestru Ancilla $ $O $.</span><span class="sxs-lookup"><span data-stu-id="84122-107">The ancilla register $a$ that $O$ acts on.</span></span>
- <span data-ttu-id="84122-108">System rejestruje $s $, na którym jest zastosowana żądana jednostka $U $, po wybraniu rejestracji $a $ w stanie $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="84122-108">The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.</span></span>

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a><span data-ttu-id="84122-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="84122-109">Remarks</span></span>

<span data-ttu-id="84122-110">Ta Oracle zdefiniowana przez $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ działa w stanie Ancilla $ \ket{s} \_ a $, aby zaimplementować jednostkę $U $ na dowolnym stanie systemu $ \ket{\psi} \_ s $ z amplitudą $ \lambda $ na podstawie oflagowanej przez $ \ket{t} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="84122-110">This oracle defined by $$ O\ket{s}\_a\ket{\psi}\_s= \lambda\ket{t}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{t^\perp}\_a\cdots $$ acts on the ancilla state $\ket{s}\_a$ to implement the unitary $U$ on any system state $\ket{\psi}\_s$ with amplitude $\lambda$ in the basis flagged by $\ket{t}\_a$.</span></span>
<span data-ttu-id="84122-111">Pierwszy parametr jest rejestrem qubit $ \ket{s} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="84122-111">The first parameter is the qubit register of $\ket{s}\_a$.</span></span> <span data-ttu-id="84122-112">Drugi parametr jest rejestrem qubit $ \ket{\psi} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="84122-112">The second parameter is the qubit register of $\ket{\psi}\_s$.</span></span>