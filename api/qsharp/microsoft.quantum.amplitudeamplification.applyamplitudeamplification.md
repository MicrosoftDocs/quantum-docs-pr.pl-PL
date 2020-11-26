---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: 0b40f94633bb43df5e64cd16d5ac8e12bcd1cc4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191571"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="cd30d-102">ApplyAmplitudeAmplification, operacja</span><span class="sxs-lookup"><span data-stu-id="cd30d-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="cd30d-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="cd30d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="cd30d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd30d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd30d-105">Stosuje wzmocnienie amplitudy w danym rejestrze, korzystając z danego zestawu faz i Oracle w celu odzwierciedlenia stanu początkowego i końcowego.</span><span class="sxs-lookup"><span data-stu-id="cd30d-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cd30d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cd30d-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="cd30d-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="cd30d-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="cd30d-108">Zestaw faz opisujących częściowe odbicia na każdym etapie algorytmu wzmocnienia amplitudy.</span><span class="sxs-lookup"><span data-stu-id="cd30d-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="cd30d-109">Zobacz @"microsoft.quantum.amplitudeamplification.standardreflectionphases" , aby zapoznać się z przykładem.</span><span class="sxs-lookup"><span data-stu-id="cd30d-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="cd30d-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="cd30d-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="cd30d-111">Oracle, który odzwierciedla informacje o stanie początkowym.</span><span class="sxs-lookup"><span data-stu-id="cd30d-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="cd30d-112">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="cd30d-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="cd30d-113">Oracle, który odzwierciedla informacje o żądanym stanie końcowym.</span><span class="sxs-lookup"><span data-stu-id="cd30d-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="cd30d-114">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd30d-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cd30d-115">Rejestr, dla którego ma zostać wykonane wzmocnienie amplitudy.</span><span class="sxs-lookup"><span data-stu-id="cd30d-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd30d-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd30d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

