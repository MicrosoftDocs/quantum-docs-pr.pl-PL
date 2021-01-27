---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByReflectionPhases
title: AmpAmpByReflectionPhases, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByReflectionPhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByReflectionPhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".
ms.openlocfilehash: 407041deb2c2253c1a2ec6f58ccb696749617577
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843979"
---
# <a name="ampampbyreflectionphases-function"></a><span data-ttu-id="cbbde-102">AmpAmpByReflectionPhases, funkcja</span><span class="sxs-lookup"><span data-stu-id="cbbde-102">AmpAmpByReflectionPhases function</span></span>

<span data-ttu-id="cbbde-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="cbbde-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="cbbde-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbbde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="cbbde-105">AmpAmpByReflectionPhases jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="cbbde-105">AmpAmpByReflectionPhases has been deprecated.</span></span> <span data-ttu-id="cbbde-106">Użyj <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="cbbde-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections> instead.</span></span>
>
> <span data-ttu-id="cbbde-107">Używaj @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".</span><span class="sxs-lookup"><span data-stu-id="cbbde-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfrompartialreflections".</span></span>



```qsharp
function AmpAmpByReflectionPhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="cbbde-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cbbde-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="cbbde-109">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="cbbde-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="cbbde-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="cbbde-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>




### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="cbbde-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="cbbde-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="cbbde-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="cbbde-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

