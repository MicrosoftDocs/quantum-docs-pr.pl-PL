---
uid: Microsoft.Quantum.AmplitudeAmplification.AmpAmpByOraclePhases
title: AmpAmpByOraclePhases, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmpAmpByOraclePhases
qsharp.summary: >-
  > [!WARNING]

  > AmpAmpByOraclePhases has been deprecated. Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.

  >

  > Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".
ms.openlocfilehash: 7d02b909604c82ecc2e5d4a59608f21939d81fd2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843992"
---
# <a name="ampampbyoraclephases-function"></a><span data-ttu-id="8b539-102">AmpAmpByOraclePhases, funkcja</span><span class="sxs-lookup"><span data-stu-id="8b539-102">AmpAmpByOraclePhases function</span></span>

<span data-ttu-id="8b539-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="8b539-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="8b539-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b539-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="8b539-105">AmpAmpByOraclePhases jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="8b539-105">AmpAmpByOraclePhases has been deprecated.</span></span> <span data-ttu-id="8b539-106">Użyj <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="8b539-106">Please use <xref:Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation> instead.</span></span>
>
> <span data-ttu-id="8b539-107">Używaj @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".</span><span class="sxs-lookup"><span data-stu-id="8b539-107">Please use @"microsoft.quantum.amplitudeamplification.amplitudeamplificationfromstatepreparation".</span></span>



```qsharp
function AmpAmpByOraclePhases (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="8b539-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8b539-108">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="8b539-109">fazy: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="8b539-109">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>




### <a name="stateoracle--stateoracle"></a><span data-ttu-id="8b539-110">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="8b539-110">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>




### <a name="idxflagqubit--int"></a><span data-ttu-id="8b539-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8b539-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>





## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="8b539-112">Output: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="8b539-112">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

