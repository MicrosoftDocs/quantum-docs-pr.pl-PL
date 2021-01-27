---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 5d50b3fdc2b0f948e93cb11b5c69403d97574ccd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843953"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="04540-102">RotationPhasesAsReflectionPhases, funkcja</span><span class="sxs-lookup"><span data-stu-id="04540-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="04540-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="04540-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="04540-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04540-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04540-105">Konwertuje fazy określone jako rotacje pojedynczej qubit na fazy określone jako częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="04540-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="04540-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="04540-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="04540-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="04540-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="04540-108">Tablica rotacji z pojedynczą qubitą do przekonwertowania na częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="04540-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="04540-109">Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="04540-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="04540-110">Operacja implementująca fazy określone jako częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="04540-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="04540-111">Odwołania</span><span class="sxs-lookup"><span data-stu-id="04540-111">References</span></span>

<span data-ttu-id="04540-112">Używamy Konwencji w</span><span class="sxs-lookup"><span data-stu-id="04540-112">We use the convention in</span></span>

- <span data-ttu-id="04540-113">[ *G.H. niskie, I. L. Czuang*](https://arxiv.org/abs/1707.05391) do odnoszące się do faz operatora odbicia z jedną qubitą.</span><span class="sxs-lookup"><span data-stu-id="04540-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>