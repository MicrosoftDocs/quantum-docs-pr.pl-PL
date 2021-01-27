---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: e64ad5ad4e975483f20f92c0b070dd6788ef296b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847453"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="d3145-102">AmplitudeAmplificationFromStatePreparation, funkcja</span><span class="sxs-lookup"><span data-stu-id="d3145-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="d3145-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d3145-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d3145-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3145-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3145-105">Wzmocnienie amplitudy przez firmy Oracle dla częściowych odbicia.</span><span class="sxs-lookup"><span data-stu-id="d3145-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d3145-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d3145-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d3145-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d3145-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="d3145-108">Fazy częściowego odbicia</span><span class="sxs-lookup"><span data-stu-id="d3145-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="d3145-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="d3145-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="d3145-110">Jednostkowa firma Oracle $A $, która przygotowuje stan początkowy</span><span class="sxs-lookup"><span data-stu-id="d3145-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="d3145-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3145-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3145-112">Indeks do flagi qubit</span><span class="sxs-lookup"><span data-stu-id="d3145-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="d3145-113">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="d3145-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d3145-114">Operacja implementująca wzmocnienie amplitudy przez firmy Oracle, które są implementowane przez częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="d3145-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3145-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d3145-115">Remarks</span></span>

<span data-ttu-id="d3145-116">To nakłada bardziej rygorystyczne warunki na formularzu stanu początkowego i docelowego niż w `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="d3145-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="d3145-117">Przyjęto założenie, że stan docelowy jest oznaczony przez $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="d3145-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="d3145-118">Przyjęto założenie, że \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} w większości przypadków `flagQubit` i `auxiliaryRegister` są inicjowane w stanie $ \ket {0} \_ {f} \ket {0} \_ s $.</span><span class="sxs-lookup"><span data-stu-id="d3145-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>