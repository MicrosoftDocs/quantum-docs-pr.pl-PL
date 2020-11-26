---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191605"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="bfb6f-102">AmplitudeAmplificationFromStatePreparation, funkcja</span><span class="sxs-lookup"><span data-stu-id="bfb6f-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="bfb6f-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="bfb6f-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="bfb6f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bfb6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bfb6f-105">Wzmocnienie amplitudy przez firmy Oracle dla częściowych odbicia.</span><span class="sxs-lookup"><span data-stu-id="bfb6f-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="bfb6f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bfb6f-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="bfb6f-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="bfb6f-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="bfb6f-108">Fazy częściowego odbicia</span><span class="sxs-lookup"><span data-stu-id="bfb6f-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="bfb6f-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="bfb6f-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="bfb6f-110">Jednostkowa firma Oracle $A $, która przygotowuje stan początkowy</span><span class="sxs-lookup"><span data-stu-id="bfb6f-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="bfb6f-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bfb6f-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bfb6f-112">Indeks do flagi qubit</span><span class="sxs-lookup"><span data-stu-id="bfb6f-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="bfb6f-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="bfb6f-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bfb6f-114">Operacja implementująca wzmocnienie amplitudy przez firmy Oracle, które są implementowane przez częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="bfb6f-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="bfb6f-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bfb6f-115">Remarks</span></span>

<span data-ttu-id="bfb6f-116">To nakłada bardziej rygorystyczne warunki na formularzu stanu początkowego i docelowego niż w `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="bfb6f-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="bfb6f-117">Przyjęto założenie, że stan docelowy jest oznaczony przez $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="bfb6f-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="bfb6f-118">Przyjęto założenie, że \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} w większości przypadków `flagQubit` i `auxiliaryRegister` są inicjowane w stanie $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="bfb6f-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>