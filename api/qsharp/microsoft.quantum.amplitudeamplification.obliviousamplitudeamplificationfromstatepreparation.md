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
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation, funkcja

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wzmocnienie amplitudy Oblivious przez firmy Oracle dla częściowych odbicia.

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="phases--reflectionphases"></a>fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fazy częściowego odbicia


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Jednostkowa baza danych Oracle $A $, która przygotowuje stan pomocniczego uruchamiania


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Jednostkowa Oracle $O $ typu `ObliviousOracle` , który działa wspólnie z rejestrem pomocniczym i systemowym


### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Indeksuj do rejestru flagi pojedynczego qubit



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Operacja implementująca wzmocnienie amplitudy Oblivious w oparciu o częściowe odbicia.

## <a name="remarks"></a>Uwagi

Stanowi to bardziej rygorystyczne warunki na formularzu pomocniczych Stanów początkowych i docelowych niż w `AmpAmpObliviousByReflectionPhases` .
Przyjęto założenie, że $A \ket {0} \_ f\ket {0} \_ A = \ket{\Text{Start}} \_ {FA} $ przygotowuje pomocniczy stan uruchomienia $ \ket{\Text{Start}} \_ {FA} $ z podstawy obliczeniowej $ \ket {0} \_ f\ket {0} $.
Przyjęto założenie, że stan docelowy jest oznaczony przez $ \ket {1} \_ f $.
Przyjęto założenie, że \begin{align} O\ket {\ Text {Start}} \_ {FA} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {cokolwiek}} \_ a\ket {\ Text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} dla niektórych jednostek $U $.