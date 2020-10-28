---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromPartialReflections
title: ObliviousAmplitudeAmplificationFromPartialReflections, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromPartialReflections
qsharp.summary: Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.
ms.openlocfilehash: 98f410e4c00e50d60d9b45b675e99396d79f955c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721839"
---
# <a name="obliviousamplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="e4e32-102">ObliviousAmplitudeAmplificationFromPartialReflections, funkcja</span><span class="sxs-lookup"><span data-stu-id="e4e32-102">ObliviousAmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="e4e32-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e4e32-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e4e32-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e4e32-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e4e32-105">Zwraca jednostkę, która implementuje wzmocnienie amplitudy Oblivious przez określenie dla częściowego odbicia.</span><span class="sxs-lookup"><span data-stu-id="e4e32-105">Returns a unitary that implements oblivious amplitude amplification by specifying for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e4e32-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e4e32-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="e4e32-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="e4e32-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="e4e32-108">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="e4e32-108">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="e4e32-109">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="e4e32-109">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="e4e32-110">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="e4e32-110">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>





## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="e4e32-111">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="e4e32-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

