---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: f9edafcce62c8b30a6bd52b7dbaa2df2c50c920d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845998"
---
# <a name="randomwalkphaseestimation-operation"></a><span data-ttu-id="f8add-102">RandomWalkPhaseEstimation, operacja</span><span class="sxs-lookup"><span data-stu-id="f8add-102">RandomWalkPhaseEstimation operation</span></span>

<span data-ttu-id="f8add-103">Przestrzeń nazw: [Microsoft. Quantum. Research. scharakteryzowanie](xref:Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f8add-103">Namespace: [Microsoft.Quantum.Research.Characterization](xref:Microsoft.Quantum.Research.Characterization)</span></span>

<span data-ttu-id="f8add-104">Pakiet: [Microsoft. Quantum. Research. scharakteryzowanie](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span><span class="sxs-lookup"><span data-stu-id="f8add-104">Package: [Microsoft.Quantum.Research.Characterization](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)</span></span>


<span data-ttu-id="f8add-105">Wykonuje iteracyjne szacowanie faz przy użyciu losowego instruktażu do przybliżonego Bayesowskieowania na podstawie wyników pomiaru klasycznego z danej bazy danych Oracle i eigenstate.</span><span class="sxs-lookup"><span data-stu-id="f8add-105">Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.</span></span>

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a><span data-ttu-id="f8add-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f8add-106">Input</span></span>

### <a name="initialmean--double"></a><span data-ttu-id="f8add-107">initialMean: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f8add-107">initialMean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f8add-108">Średnia początkowej normalnej dystrybucji poprzedniej niż $ \phi $.</span><span class="sxs-lookup"><span data-stu-id="f8add-108">Mean of the initial normal prior distribution over $\phi$.</span></span>


### <a name="initialstddev--double"></a><span data-ttu-id="f8add-109">initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f8add-109">initialStdDev : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f8add-110">Odchylenie standardowe początkowej normalnej poprzedniej dystrybucji powyżej $ \phi $.</span><span class="sxs-lookup"><span data-stu-id="f8add-110">Standard deviation of the initial normal prior distribution over $\phi$.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="f8add-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8add-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8add-112">Liczba pomiarów, które mają zostać zaakceptowane do końcowego oszacowania ostatecznego.</span><span class="sxs-lookup"><span data-stu-id="f8add-112">Number of measurements to be accepted into the final posterior estimate.</span></span>


### <a name="maxmeasurements--int"></a><span data-ttu-id="f8add-113">maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8add-113">maxMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8add-114">Łączna liczba pomiarów, niż można wykonać, zanim operacja zostanie uznana za niepowodzenie.</span><span class="sxs-lookup"><span data-stu-id="f8add-114">Total number of measurements than can be taken before the operation is considered to have failed.</span></span>


### <a name="unwind--int"></a><span data-ttu-id="f8add-115">unwinde: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f8add-115">unwind : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f8add-116">Liczba wyników, które należy zapomnieć, gdy sprawdzanie spójności zakończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="f8add-116">Number of results to forget when consistency checks fail.</span></span>


### <a name="oracle--continuousoracle"></a><span data-ttu-id="f8add-117">Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span><span class="sxs-lookup"><span data-stu-id="f8add-117">oracle : [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)</span></span>

<span data-ttu-id="f8add-118">Operacja reprezentująca $U jednostkową $, która $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ dla eigenstates $ \ket{\phi} $ z nieznaną fazą $ \phi \In \mathbb{R} ^ + $.</span><span class="sxs-lookup"><span data-stu-id="f8add-118">An operation representing a unitary $U$ such that $U(t)\ket{\phi} = e^{i t \phi}\ket{\phi}$ for eigenstates $\ket{\phi}$ with unknown phase $\phi \in \mathbb{R}^+$.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="f8add-119">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f8add-119">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f8add-120">Rejestr, który $U $ działa.</span><span class="sxs-lookup"><span data-stu-id="f8add-120">A register that $U$ acts on.</span></span>



## <a name="output--double"></a><span data-ttu-id="f8add-121">Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f8add-121">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f8add-122">Ostateczne oszacowanie $ \hat{\phi} \mathrel{: =} \expect [\phi] $, gdzie oczekiwana jest ponad końcową daną wszystkie zaakceptowane dane.</span><span class="sxs-lookup"><span data-stu-id="f8add-122">The final estimate $\hat{\phi} \mathrel{:=} \expect[\phi]$ , where the expectation is over the posterior given all accepted data.</span></span>

## <a name="remarks"></a><span data-ttu-id="f8add-123">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f8add-123">Remarks</span></span>

### <a name="iterative-phase-estimation-and-eigenstates"></a><span data-ttu-id="f8add-124">Szacowanie fazy iteracyjnej i Eigenstates</span><span class="sxs-lookup"><span data-stu-id="f8add-124">Iterative Phase Estimation and Eigenstates</span></span>

<span data-ttu-id="f8add-125">Ogólnie rzecz biorąc, rejestr wejściowy `eigenstate` nie musi być eigenstate $ \ket{\phi} $ $U $, ale może być nadpozycją w przedziale eigenstates.</span><span class="sxs-lookup"><span data-stu-id="f8add-125">In general, the input register `eigenstate` need not be an eigenstate $\ket{\phi}$ of $U$, but can be a superposition over eigenstates.</span></span> <span data-ttu-id="f8add-126">Załóżmy, że stan danych wejściowych jest określony przez \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\phi \_ j}, \end{align} gdzie $ \{ \Alpha \_ j \} $ to złożone współczynniki, takie jak $ \sum \_ j | \Alpha \_ j | ^ 2 = $1 i gdzie $U \ket{\phi \_ j} = \phi \_ j\ket {\ Fi \_ j} $.</span><span class="sxs-lookup"><span data-stu-id="f8add-126">Suppose that the input state is given by \begin{align} \ket{\psi} & = \sum\_{j} \alpha\_j \ket{\phi\_j}, \end{align} where $\{\alpha\_j\}$ are complex coefficients such that $\sum\_j |\alpha\_j|^2 = 1$ and where $U\ket{\phi\_j} = \phi\_j\ket{\phi\_j}$.</span></span>

<span data-ttu-id="f8add-127">Następnie wykonywanie szacowania fazy iteracyjnej ostatecznie wywoła zbieżność do jednego eigenstateu, zgodnie z opisem w [przewodniku programistycznym](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span><span class="sxs-lookup"><span data-stu-id="f8add-127">Then, performing iterative phase estimation will eventually converge to a single eigenstate, as described in the [development guide](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).</span></span>

### <a name="experiment-design"></a><span data-ttu-id="f8add-128">Projekt eksperymentu</span><span class="sxs-lookup"><span data-stu-id="f8add-128">Experiment Design</span></span>

<span data-ttu-id="f8add-129">Czasy pomiaru $t $ i niezgodne ze kątami $ \theta $ `oracle` są wybierane zgodnie z *algorytmem heurystycznego zgadywania cząsteczek*, \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.</span><span class="sxs-lookup"><span data-stu-id="f8add-129">The measurement times $t$ and inversion angles $\theta$ passed to `oracle` are chosen according to the *particle guess heuristic*, \begin{align} \theta \sim \Pr(\phi),\quad t \approx \frac{1}{\variance{\phi}}.</span></span>
<span data-ttu-id="f8add-130">\end{align} ten algorytm heurystyczny jest optymalny, aby zmniejszyć oczekiwaną wariancję w fazie iteracji, w ramach założeń normalnych przed.</span><span class="sxs-lookup"><span data-stu-id="f8add-130">\end{align} This heuristic is optimal for reducing the expected posterior variance in iterative phase estimation under the assumption of a normal prior.</span></span>

### <a name="optimality"></a><span data-ttu-id="f8add-131">Optymalność</span><span class="sxs-lookup"><span data-stu-id="f8add-131">Optimality</span></span>

<span data-ttu-id="f8add-132">Ta operacja przybliża optymalną szacowaniaę dla fazy $ \phi $, która została oceniona przy użyciu $L ubytku kwadratu (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="f8add-132">This operation approximates the optimal estimator for the phase $\phi$, as evaluated using the quadratic loss $L(\phi, \hat{\phi}) \mathrel{:=} (\phi - \hat{\phi})^2$.</span></span>

<span data-ttu-id="f8add-133">Zobacz [bayesowskie fazy szacowania](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) , aby uzyskać więcej szczegółów na temat statystyk oszacowania fazy iteracji.</span><span class="sxs-lookup"><span data-stu-id="f8add-133">See [Bayesian Phase Estimation](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) for more details on the statistics of iterative phase estimation.</span></span>

## <a name="references"></a><span data-ttu-id="f8add-134">Odwołania</span><span class="sxs-lookup"><span data-stu-id="f8add-134">References</span></span>

- <span data-ttu-id="f8add-135">Odwołujące *et al.* 2011 [DOI: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [ArXiv: 1110.3067](https://arxiv.org/abs/1110.3067).</span><span class="sxs-lookup"><span data-stu-id="f8add-135">Ferrie *et al.* 2011 [doi:10/tfx](https://doi.org/10.1007/s11128-012-0407-6), [arXiv:1110.3067](https://arxiv.org/abs/1110.3067).</span></span>
- <span data-ttu-id="f8add-136">Wiebe *et al.* 2013 [DOI: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [ArXiv: 1309.0876](https://arxiv.org/abs/1309.0876)</span><span class="sxs-lookup"><span data-stu-id="f8add-136">Wiebe *et al.* 2013 [doi:10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501), [arXiv:1309.0876](https://arxiv.org/abs/1309.0876)</span></span>
- <span data-ttu-id="f8add-137">Wiebe i granade 2018 *(w przygotowaniu)*.</span><span class="sxs-lookup"><span data-stu-id="f8add-137">Wiebe and Granade 2018 *(in preparation)*.</span></span>