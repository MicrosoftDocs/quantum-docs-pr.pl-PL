---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721942"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="7f28e-102">AmplitudeAmplificationFromStatePreparation, funkcja</span><span class="sxs-lookup"><span data-stu-id="7f28e-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="7f28e-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="7f28e-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="7f28e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f28e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f28e-105">Wzmocnienie amplitudy przez firmy Oracle dla częściowych odbicia.</span><span class="sxs-lookup"><span data-stu-id="7f28e-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="7f28e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7f28e-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="7f28e-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="7f28e-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="7f28e-108">Fazy częściowego odbicia</span><span class="sxs-lookup"><span data-stu-id="7f28e-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="7f28e-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="7f28e-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="7f28e-110">Jednostkowa firma Oracle $A $, która przygotowuje stan początkowy</span><span class="sxs-lookup"><span data-stu-id="7f28e-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="7f28e-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7f28e-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7f28e-112">Indeks do flagi qubit</span><span class="sxs-lookup"><span data-stu-id="7f28e-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="7f28e-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="7f28e-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="7f28e-114">Operacja implementująca wzmocnienie amplitudy przez firmy Oracle, które są implementowane przez częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="7f28e-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f28e-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="7f28e-115">Remarks</span></span>

<span data-ttu-id="7f28e-116">To nakłada bardziej rygorystyczne warunki na formularzu stanu początkowego i docelowego niż w `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="7f28e-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="7f28e-117">Przyjęto założenie, że stan docelowy jest oznaczony przez $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="7f28e-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="7f28e-118">Przyjęto założenie, że \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} w większości przypadków `flagQubit` i `auxiliaryRegister` są inicjowane w stanie $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="7f28e-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>