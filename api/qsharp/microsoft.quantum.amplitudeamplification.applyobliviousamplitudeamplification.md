---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: a1bda344b1097c7ab3240bc6d9cd0d8df80b9662
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721881"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>ApplyObliviousAmplitudeAmplification, operacja

Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Package [](https://nuget.org/packages/)


Wzmocnienie amplitudy Oblivious, określając częściowe odbicie.

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="phases--reflectionphases"></a>fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

Fazy częściowego odbicia


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operator odbicia informacji o stanie początkowym rejestracji pomocniczej


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Operator odbicia dotyczący stanu docelowego rejestru pomocniczego


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Jednostkowa Oracle $O $ typu `ObliviousOracle` , który działa wspólnie z rejestrami pomocniczymi i systemowymi.


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr pomocniczy


### <a name="systemregister--qubit"></a>systemRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Rejestr systemu



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Mając określony pomocniczy stan uruchomienia $ \ket{\Text{Start}} \_ a $, określony pomocniczy stan docelowy $ \ket{\Text{Target}} \_ a $ i dowolny stan systemu $ \ket{\psi} \_ s $, Załóżmy, że \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\Text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\Text{Target} ^ \perp} \_ a\cdots \end{align} dla niektórych jednostek $U $.
Przez sekwencję odbić o stanie początkowym i docelowym w odniesieniu do rejestru pomocniczego, w którym `signalOracle` są stosowane aplikacje i jej sąsiadujące, prawdopodobieństwo sukcesu zastosowania U może ulec zmianie.

W większości przypadków `auxiliaryRegister` jest inicjowany w stanie $ \ket{\Text{Start}} \_ a $.

## <a name="references"></a>Dokumentacja

Zobacz

- [ *D.W. jagody, A.M., dzieci, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) dla wersji Standard.
  Zobacz
- [ *G.H. Low, I.L. Czuang,*](https://arxiv.org/abs/1610.06546) aby uogólnić częściowe odbicie.