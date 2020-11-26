---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: 9b0060201bcdae02a207362a753a0a403cdbb896
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191520"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="a4f05-102">ApplyObliviousAmplitudeAmplification, operacja</span><span class="sxs-lookup"><span data-stu-id="a4f05-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="a4f05-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a4f05-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a4f05-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a4f05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a4f05-105">Wzmocnienie amplitudy Oblivious, określając częściowe odbicie.</span><span class="sxs-lookup"><span data-stu-id="a4f05-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a4f05-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a4f05-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="a4f05-107">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="a4f05-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="a4f05-108">Fazy częściowego odbicia</span><span class="sxs-lookup"><span data-stu-id="a4f05-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="a4f05-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a4f05-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a4f05-110">Operator odbicia informacji o stanie początkowym rejestracji pomocniczej</span><span class="sxs-lookup"><span data-stu-id="a4f05-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="a4f05-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="a4f05-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="a4f05-112">Operator odbicia dotyczący stanu docelowego rejestru pomocniczego</span><span class="sxs-lookup"><span data-stu-id="a4f05-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="a4f05-113">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="a4f05-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="a4f05-114">Jednostkowa Oracle $O $ typu `ObliviousOracle` , który działa wspólnie z rejestrami pomocniczymi i systemowymi.</span><span class="sxs-lookup"><span data-stu-id="a4f05-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="a4f05-115">auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a4f05-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a4f05-116">Rejestr pomocniczy</span><span class="sxs-lookup"><span data-stu-id="a4f05-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="a4f05-117">systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a4f05-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a4f05-118">Rejestr systemu</span><span class="sxs-lookup"><span data-stu-id="a4f05-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="a4f05-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a4f05-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a4f05-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a4f05-120">Remarks</span></span>

<span data-ttu-id="a4f05-121">Mając określony pomocniczy stan uruchomienia $ \ket{\Text{Start}} \_ a $, określony pomocniczy stan docelowy $ \ket{\Text{Target}} \_ a $ i dowolny stan systemu $ \ket{\psi} \_ s $, Załóżmy, że \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\Text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\Text{Target} ^ \perp} \_ a\cdots \end{align} dla niektórych jednostek $U $.</span><span class="sxs-lookup"><span data-stu-id="a4f05-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="a4f05-122">Przez sekwencję odbić o stanie początkowym i docelowym w odniesieniu do rejestru pomocniczego, w którym `signalOracle` są stosowane aplikacje i jej sąsiadujące, prawdopodobieństwo sukcesu zastosowania U może ulec zmianie.</span><span class="sxs-lookup"><span data-stu-id="a4f05-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="a4f05-123">W większości przypadków `auxiliaryRegister` jest inicjowany w stanie $ \ket{\Text{Start}} \_ a $.</span><span class="sxs-lookup"><span data-stu-id="a4f05-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="a4f05-124">Odwołania</span><span class="sxs-lookup"><span data-stu-id="a4f05-124">References</span></span>

<span data-ttu-id="a4f05-125">Zobacz</span><span class="sxs-lookup"><span data-stu-id="a4f05-125">See</span></span>

- <span data-ttu-id="a4f05-126">[ *D.W. jagody, A.M., dzieci, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) dla wersji Standard.</span><span class="sxs-lookup"><span data-stu-id="a4f05-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="a4f05-127">Zobacz</span><span class="sxs-lookup"><span data-stu-id="a4f05-127">See</span></span>
- <span data-ttu-id="a4f05-128">[ *G.H. Low, I.L. Czuang,*](https://arxiv.org/abs/1610.06546) aby uogólnić częściowe odbicie.</span><span class="sxs-lookup"><span data-stu-id="a4f05-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>