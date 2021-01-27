---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhases
title: RotationPhases typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhases
qsharp.summary: Phases for a sequence of single-qubit rotations in amplitude amplification.
ms.openlocfilehash: 2f955ce3bfb9ea057c26c79547895df39ed322ab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843966"
---
# <a name="rotationphases-user-defined-type"></a><span data-ttu-id="152da-102">RotationPhases typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="152da-102">RotationPhases user defined type</span></span>

<span data-ttu-id="152da-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="152da-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="152da-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="152da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="152da-105">Fazy dla sekwencji rotacji z pojedynczą qubitą w wzmocnienie amplitudy.</span><span class="sxs-lookup"><span data-stu-id="152da-105">Phases for a sequence of single-qubit rotations in amplitude amplification.</span></span>

```qsharp

newtype RotationPhases = (Double[]);
```



## <a name="remarks"></a><span data-ttu-id="152da-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="152da-106">Remarks</span></span>

<span data-ttu-id="152da-107">Pierwszy parametr jest tablicą faz dla odbić, wyrażoną jako iloczyn pojedynczej rotacji qubit.</span><span class="sxs-lookup"><span data-stu-id="152da-107">The first parameter is an array of phases for reflections, expressed as a product of single-qubit rotations.</span></span>
<span data-ttu-id="152da-108">[ G.H.</span><span class="sxs-lookup"><span data-stu-id="152da-108">[ G.H.</span></span> <span data-ttu-id="152da-109">Niski, I. L.</span><span class="sxs-lookup"><span data-stu-id="152da-109">Low, I. L.</span></span> <span data-ttu-id="152da-110">Czuang, https://arxiv.org/abs/1707.05391 ].</span><span class="sxs-lookup"><span data-stu-id="152da-110">Chuang, https://arxiv.org/abs/1707.05391].</span></span>