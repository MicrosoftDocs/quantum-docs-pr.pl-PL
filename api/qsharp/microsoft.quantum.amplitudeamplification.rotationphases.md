---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: b0373f964b77f8ea561c6e96b11e476b42e7fc55
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721769"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="cbdac-102">RotationPhases typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="cbdac-102">RotationPhases user defined type</span></span>

<span data-ttu-id="cbdac-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="cbdac-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="cbdac-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cbdac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cbdac-105">Fazy dla sekwencji rotacji z pojedynczą qubitą w wzmocnienie amplitudy.</span><span class="sxs-lookup"><span data-stu-id="cbdac-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="cbdac-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="cbdac-106">Remarks</span></span>

<span data-ttu-id="cbdac-107">Pierwszy parametr jest tablicą faz dla odbić, wyrażoną jako iloczyn pojedynczej rotacji qubit.</span><span class="sxs-lookup"><span data-stu-id="cbdac-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="cbdac-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="cbdac-108">[ G.H.</span></span> <span data-ttu-id="cbdac-109">Niski, I. L.</span><span class="sxs-lookup"><span data-stu-id="cbdac-109">Low, I. L.</span></span> <span data-ttu-id="cbdac-110">Czuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="cbdac-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>