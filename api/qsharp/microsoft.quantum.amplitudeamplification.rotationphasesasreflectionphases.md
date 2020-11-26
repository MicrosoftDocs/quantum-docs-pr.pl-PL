---
uid: Microsoft.Quantum.AmplitudeAmplification.RotationPhasesAsReflectionPhases
title: RotationPhasesAsReflectionPhases, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: RotationPhasesAsReflectionPhases
qsharp.summary: Converts phases specified as single-qubit rotations to phases specified as partial reflections.
ms.openlocfilehash: 6e601cfd867b449d628da7cd60dfacd465e48860
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191197"
---
# <a name="rotationphasesasreflectionphases-function"></a><span data-ttu-id="af407-102">RotationPhasesAsReflectionPhases, funkcja</span><span class="sxs-lookup"><span data-stu-id="af407-102">RotationPhasesAsReflectionPhases function</span></span>

<span data-ttu-id="af407-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="af407-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="af407-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="af407-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="af407-105">Konwertuje fazy określone jako rotacje pojedynczej qubit na fazy określone jako częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="af407-105">Converts phases specified as single-qubit rotations to phases specified as partial reflections.</span></span>

```qsharp
function RotationPhasesAsReflectionPhases (rotPhases : Microsoft.Quantum.AmplitudeAmplification.RotationPhases) : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases
```


## <a name="input"></a><span data-ttu-id="af407-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="af407-106">Input</span></span>

### <a name="rotphases--rotationphases"></a><span data-ttu-id="af407-107">rotPhases: [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span><span class="sxs-lookup"><span data-stu-id="af407-107">rotPhases : [RotationPhases](xref:Microsoft.Quantum.AmplitudeAmplification.RotationPhases)</span></span>

<span data-ttu-id="af407-108">Tablica rotacji z pojedynczą qubitą do przekonwertowania na częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="af407-108">Array of single-qubit rotations to be converted to partial reflections.</span></span>



## <a name="output--reflectionphases"></a><span data-ttu-id="af407-109">Wynik: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="af407-109">Output : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="af407-110">Operacja implementująca fazy określone jako częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="af407-110">An operation that implements phases specified as partial reflections.</span></span>

## <a name="references"></a><span data-ttu-id="af407-111">Odwołania</span><span class="sxs-lookup"><span data-stu-id="af407-111">References</span></span>

<span data-ttu-id="af407-112">Używamy Konwencji w</span><span class="sxs-lookup"><span data-stu-id="af407-112">We use the convention in</span></span>

- <span data-ttu-id="af407-113">[ *G.H. niskie, I. L. Czuang*](https://arxiv.org/abs/1707.05391) do odnoszące się do faz operatora odbicia z jedną qubitą.</span><span class="sxs-lookup"><span data-stu-id="af407-113">[ *G.H. Low, I. L. Chuang* ](https://arxiv.org/abs/1707.05391) for relating single-qubit rotation phases to reflection operator phases.</span></span>