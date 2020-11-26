---
uid: Microsoft.Quantum.Preparation.MixedStatePreparation
title: MixedStatePreparation typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: MixedStatePreparation
qsharp.summary: Represents a particular mixed state that can be prepared on an index and a garbage register.
ms.openlocfilehash: 94d6483914b5d21bb51a5469c7123f834e9eb5da
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193577"
---
# <a name="mixedstatepreparation-user-defined-type"></a><span data-ttu-id="9e9a4-102">MixedStatePreparation typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="9e9a4-102">MixedStatePreparation user defined type</span></span>

<span data-ttu-id="9e9a4-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="9e9a4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="9e9a4-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e9a4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e9a4-105">Reprezentuje konkretny stan mieszany, który można przygotować na indeksie i rejestrze elementów bezużytecznych.</span><span class="sxs-lookup"><span data-stu-id="9e9a4-105">Represents a particular mixed state that can be prepared on an index and a garbage register.</span></span>

```qsharp

newtype MixedStatePreparation = (Requirements : Microsoft.Quantum.Preparation.MixedStatePreparationRequirements, Norm : Double, Prepare : ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="9e9a4-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="9e9a4-106">Named Items</span></span>

### <a name="requirements--mixedstatepreparationrequirements"></a><span data-ttu-id="9e9a4-107">Wymagania: [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span><span class="sxs-lookup"><span data-stu-id="9e9a4-107">Requirements : [MixedStatePreparationRequirements](xref:Microsoft.Quantum.Preparation.MixedStatePreparationRequirements)</span></span>


### <a name="norm--double"></a><span data-ttu-id="9e9a4-108">Norma: [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9e9a4-108">Norm : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>


### <a name="prepare--littleendianqubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="9e9a4-109">Prepare: ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="9e9a4-109">Prepare : ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>



## <a name="see-also"></a><span data-ttu-id="9e9a4-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9e9a4-110">See Also</span></span>

- [<span data-ttu-id="9e9a4-111">Microsoft. Quantum. PurifiedMixedState</span><span class="sxs-lookup"><span data-stu-id="9e9a4-111">Microsoft.Quantum.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.PurifiedMixedState)