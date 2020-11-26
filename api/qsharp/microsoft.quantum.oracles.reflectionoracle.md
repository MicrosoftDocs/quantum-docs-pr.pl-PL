---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226659"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="e11c8-102">ReflectionOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="e11c8-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="e11c8-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="e11c8-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="e11c8-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e11c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e11c8-105">Reprezentuje odbicie Oracle.</span><span class="sxs-lookup"><span data-stu-id="e11c8-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="e11c8-106">Odbicie Oracle, $O $, ma dane wejściowe:</span><span class="sxs-lookup"><span data-stu-id="e11c8-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="e11c8-107">Faza $ \phi $, przez którą ma zostać obrócony odbicie.</span><span class="sxs-lookup"><span data-stu-id="e11c8-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="e11c8-108">Rejestr qubit, w którym ma zostać wykonane odpowiednie odbicie.</span><span class="sxs-lookup"><span data-stu-id="e11c8-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="e11c8-109">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="e11c8-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a><span data-ttu-id="e11c8-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="e11c8-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="e11c8-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e11c8-111">Remarks</span></span>

<span data-ttu-id="e11c8-112">Ta Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ wykonuje częściowe odbicie według fazy $ \phi $ o pojedynczym czystym stanie $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="e11c8-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>