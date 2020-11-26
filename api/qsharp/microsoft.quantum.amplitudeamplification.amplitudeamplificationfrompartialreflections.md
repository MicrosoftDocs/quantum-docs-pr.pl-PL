---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: 8fa6db7d5616f8c561191e3da00a69b05041b279
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191690"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="d7e18-102">AmplitudeAmplificationFromPartialReflections, funkcja</span><span class="sxs-lookup"><span data-stu-id="d7e18-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="d7e18-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d7e18-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d7e18-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d7e18-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d7e18-105">Wzmocnienie amplitudy poprzez częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="d7e18-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d7e18-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d7e18-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d7e18-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d7e18-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="d7e18-108">Fazy częściowego odbicia</span><span class="sxs-lookup"><span data-stu-id="d7e18-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="d7e18-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d7e18-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d7e18-110">Operator odbicia informacji o stanie uruchamiania</span><span class="sxs-lookup"><span data-stu-id="d7e18-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="d7e18-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d7e18-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d7e18-112">Operator odbicia dotyczący stanu docelowego</span><span class="sxs-lookup"><span data-stu-id="d7e18-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="d7e18-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="d7e18-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d7e18-114">Operacja implementująca wzmocnienie amplitudy poprzez częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="d7e18-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="d7e18-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d7e18-115">Remarks</span></span>

<span data-ttu-id="d7e18-116">Wzmocnienie amplitudy jest szczególnym przypadkiem wzmocnienia amplitudy Oblivious, w którym nie ma qubits systemowej, a Oblivious Oracle jest ustawiona na tożsamość.</span><span class="sxs-lookup"><span data-stu-id="d7e18-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="d7e18-117">W większości przypadków `startQubits` jest inicjowany w stanie $ \ket{\text{start}} \_ $1, który jest eigenstate $-$1 `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="d7e18-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>