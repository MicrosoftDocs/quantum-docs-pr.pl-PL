---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721909"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="145c5-102">ApplyFixedPointAmplification, operacja</span><span class="sxs-lookup"><span data-stu-id="145c5-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="145c5-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="145c5-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="145c5-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="145c5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="145c5-105">Algorytm wzmocnienia amplitudy Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="145c5-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="145c5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="145c5-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="145c5-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="145c5-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="145c5-108">Moduł firmy Oracle, który przygotowuje stan uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="145c5-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="145c5-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="145c5-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="145c5-110">Rejestr qubit</span><span class="sxs-lookup"><span data-stu-id="145c5-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="145c5-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="145c5-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="145c5-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="145c5-112">Remarks</span></span>

<span data-ttu-id="145c5-113">StartQubits musi znajdować się w stanie $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="145c5-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="145c5-114">Ta operacja wykonuje iterację na wielu zapytaniach w uprawnieniach $2 $ do momentu osiągnięcia maksymalnej liczby zapytań lub znalezienia stanu docelowego.</span><span class="sxs-lookup"><span data-stu-id="145c5-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>