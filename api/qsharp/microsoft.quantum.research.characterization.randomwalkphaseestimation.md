---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 2c3afdd41da24a1f32f59f36f0f5c5ed29df1f0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226166"
---
# <a name="randomwalkphaseestimation-operation"></a>RandomWalkPhaseEstimation, operacja

Przestrzeń nazw: [Microsoft. Quantum. Research. scharakteryzowanie](xref:Microsoft.Quantum.Research.Characterization)

Pakiet: [Microsoft. Quantum. Research. scharakteryzowanie](https://nuget.org/packages/Microsoft.Quantum.Research.Characterization)


Wykonuje iteracyjne szacowanie faz przy użyciu losowego instruktażu do przybliżonego Bayesowskieowania na podstawie wyników pomiaru klasycznego z danej bazy danych Oracle i eigenstate.

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>Dane wejściowe

### <a name="initialmean--double"></a>initialMean: [Double](xref:microsoft.quantum.lang-ref.double)

Średnia początkowej normalnej dystrybucji poprzedniej niż $ \phi $.


### <a name="initialstddev--double"></a>initialStdDev: [Double](xref:microsoft.quantum.lang-ref.double)

Odchylenie standardowe początkowej normalnej poprzedniej dystrybucji powyżej $ \phi $.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Liczba pomiarów, które mają zostać zaakceptowane do końcowego oszacowania ostatecznego.


### <a name="maxmeasurements--int"></a>maxMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Łączna liczba pomiarów, niż można wykonać, zanim operacja zostanie uznana za niepowodzenie.


### <a name="unwind--int"></a>unwinde: [int](xref:microsoft.quantum.lang-ref.int)

Liczba wyników, które należy zapomnieć, gdy sprawdzanie spójności zakończy się niepowodzeniem.


### <a name="oracle--continuousoracle"></a>Oracle: [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

Operacja reprezentująca $U jednostkową $, która $U (t) \ket{\phi} = e ^ {i t \phi}\ket{\phi} $ dla eigenstates $ \ket{\phi} $ z nieznaną fazą $ \phi \In \mathbb{R} ^ + $.


### <a name="targetstate--qubit"></a>targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr, który $U $ działa.



## <a name="output--double"></a>Dane wyjściowe: [Double](xref:microsoft.quantum.lang-ref.double)

Ostateczne oszacowanie $ \hat{\phi} \mathrel{: =} \expect [\phi] $, gdzie oczekiwana jest ponad końcową daną wszystkie zaakceptowane dane.

## <a name="remarks"></a>Uwagi

### <a name="iterative-phase-estimation-and-eigenstates"></a>Szacowanie fazy iteracyjnej i Eigenstates

Ogólnie rzecz biorąc, rejestr wejściowy `eigenstate` nie musi być eigenstate $ \ket{\phi} $ $U $, ale może być nadpozycją w przedziale eigenstates. Załóżmy, że stan danych wejściowych jest określony przez \begin{align} \ket{\psi} & = \sum \_ {j} \Alpha \_ j \ket{\phi \_ j}, \end{align} gdzie $ \{ \Alpha \_ j \} $ to złożone współczynniki, takie jak $ \sum \_ j | \Alpha \_ j | ^ 2 = $1 i gdzie $U \ket{\phi \_ j} = \phi \_ j\ket {\ Fi \_ j} $.

Następnie wykonywanie szacowania fazy iteracyjnej ostatecznie wywoła zbieżność do jednego eigenstateu, zgodnie z opisem w [przewodniku programistycznym](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates).

### <a name="experiment-design"></a>Projekt eksperymentu

Czasy pomiaru $t $ i niezgodne ze kątami $ \theta $ `oracle` są wybierane zgodnie z *algorytmem heurystycznego zgadywania cząsteczek*, \Begin{align} \theta \sim \Pr (\phi), \quad t \approx \frac {1} {\variance{\phi}}.
\end{align} ten algorytm heurystyczny jest optymalny, aby zmniejszyć oczekiwaną wariancję w fazie iteracji, w ramach założeń normalnych przed.

### <a name="optimality"></a>Optymalność

Ta operacja przybliża optymalną szacowaniaę dla fazy $ \phi $, która została oceniona przy użyciu $L ubytku kwadratu (\phi, \hat{\phi}) \mathrel{: =} (\phi-\hat{\phi}) ^ 2 $.

Zobacz [bayesowskie fazy szacowania](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) , aby uzyskać więcej szczegółów na temat statystyk oszacowania fazy iteracji.

## <a name="references"></a>Odwołania

- Odwołujące *et al.* 2011 [DOI: 10/TFX](https://doi.org/10.1007/s11128-012-0407-6), [ArXiv: 1110.3067](https://arxiv.org/abs/1110.3067).
- Wiebe *et al.* 2013 [DOI: 10/TF3](https://doi.org/10.1103/PhysRevLett.112.190501), [ArXiv: 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe i granade 2018 *(w przygotowaniu)*.