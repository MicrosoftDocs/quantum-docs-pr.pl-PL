---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 44bb394b0eb4ec98fd47fd1b156410b7a33903f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191299"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="58557-102">ObliviousAmplitudeAmplificationFromStatePreparation, funkcja</span><span class="sxs-lookup"><span data-stu-id="58557-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="58557-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="58557-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="58557-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="58557-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="58557-105">Wzmocnienie amplitudy Oblivious przez firmy Oracle dla częściowych odbicia.</span><span class="sxs-lookup"><span data-stu-id="58557-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="58557-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="58557-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="58557-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="58557-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="58557-108">Fazy częściowego odbicia</span><span class="sxs-lookup"><span data-stu-id="58557-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="58557-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="58557-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="58557-110">Jednostkowa baza danych Oracle $A $, która przygotowuje stan pomocniczego uruchamiania</span><span class="sxs-lookup"><span data-stu-id="58557-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="58557-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="58557-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="58557-112">Jednostkowa Oracle $O $ typu `ObliviousOracle` , który działa wspólnie z rejestrem pomocniczym i systemowym</span><span class="sxs-lookup"><span data-stu-id="58557-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="58557-113">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="58557-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="58557-114">Indeksuj do rejestru flagi pojedynczego qubit</span><span class="sxs-lookup"><span data-stu-id="58557-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit--is-adj--ctl"></a><span data-ttu-id="58557-115">Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="58557-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="58557-116">Operacja implementująca wzmocnienie amplitudy Oblivious w oparciu o częściowe odbicia.</span><span class="sxs-lookup"><span data-stu-id="58557-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="58557-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="58557-117">Remarks</span></span>

<span data-ttu-id="58557-118">Stanowi to bardziej rygorystyczne warunki na formularzu pomocniczych Stanów początkowych i docelowych niż w `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="58557-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="58557-119">Przyjęto założenie, że $A \ket {0} \_ f\ket {0} \_ A = \ket{\Text{Start}} \_ {FA} $ przygotowuje pomocniczy stan uruchomienia $ \ket{\Text{Start}} \_ {FA} $ z podstawy obliczeniowej $ \ket {0} \_ f\ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="58557-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="58557-120">Przyjęto założenie, że stan docelowy jest oznaczony przez $ \ket {1} \_ f $.</span><span class="sxs-lookup"><span data-stu-id="58557-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="58557-121">Przyjęto założenie, że \begin{align} O\ket {\ Text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {cokolwiek}} \_ a\ket {\ Text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} dla niektórych jednostek $U $.</span><span class="sxs-lookup"><span data-stu-id="58557-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>