---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724210"
---
# <a name="reflectionoracle-user-defined-type"></a><span data-ttu-id="de218-102">ReflectionOracle typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="de218-102">ReflectionOracle user defined type</span></span>

<span data-ttu-id="de218-103">Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="de218-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="de218-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de218-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de218-105">Reprezentuje odbicie Oracle.</span><span class="sxs-lookup"><span data-stu-id="de218-105">Represents a reflection oracle.</span></span>

<span data-ttu-id="de218-106">Odbicie Oracle, $O $, ma dane wejściowe:</span><span class="sxs-lookup"><span data-stu-id="de218-106">A reflection oracle, $O$, has inputs:</span></span>

- <span data-ttu-id="de218-107">Faza $ \phi $, przez którą ma zostać obrócony odbicie.</span><span class="sxs-lookup"><span data-stu-id="de218-107">The phase $\phi$ by which to rotate the reflected subspace.</span></span>
- <span data-ttu-id="de218-108">Rejestr qubit, w którym ma zostać wykonane odpowiednie odbicie.</span><span class="sxs-lookup"><span data-stu-id="de218-108">The qubit register on which to perform the given reflection.</span></span>

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="de218-109">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="de218-109">Named Items</span></span>

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a><span data-ttu-id="de218-110">ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="de218-110">ApplyReflection : ([Double](xref:microsoft.quantum.lang-ref.double),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>



## <a name="remarks"></a><span data-ttu-id="de218-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="de218-111">Remarks</span></span>

<span data-ttu-id="de218-112">Ta Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ wykonuje częściowe odbicie według fazy $ \phi $ o pojedynczym czystym stanie $ \ket{\psi} $.</span><span class="sxs-lookup"><span data-stu-id="de218-112">This oracle $O = \boldone - (1 - e^{i \phi}) \ket{\psi}\bra{\psi}$ performs a partial reflection by a phase $\phi$ about a single pure state $\ket{\psi}$.</span></span>