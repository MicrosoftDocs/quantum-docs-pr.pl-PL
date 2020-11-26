---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191537"
---
# <a name="applyfixedpointamplification-operation"></a><span data-ttu-id="2640e-102">ApplyFixedPointAmplification, operacja</span><span class="sxs-lookup"><span data-stu-id="2640e-102">ApplyFixedPointAmplification operation</span></span>

<span data-ttu-id="2640e-103">Przestrzeń nazw: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="2640e-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="2640e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2640e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2640e-105">Algorytm wzmocnienia amplitudy Fixed-Point</span><span class="sxs-lookup"><span data-stu-id="2640e-105">Fixed-Point Amplitude Amplification algorithm</span></span>

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2640e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2640e-106">Input</span></span>

### <a name="statepreporacle--stateoracle"></a><span data-ttu-id="2640e-107">statePrepOracle: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="2640e-107">statePrepOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="2640e-108">Moduł firmy Oracle, który przygotowuje stan uruchomienia.</span><span class="sxs-lookup"><span data-stu-id="2640e-108">Unitary oracle that prepares the start state.</span></span>


### <a name="startqubits--qubit"></a><span data-ttu-id="2640e-109">startQubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2640e-109">startQubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2640e-110">Rejestr qubit</span><span class="sxs-lookup"><span data-stu-id="2640e-110">Qubit register</span></span>



## <a name="output--unit"></a><span data-ttu-id="2640e-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2640e-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2640e-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="2640e-112">Remarks</span></span>

<span data-ttu-id="2640e-113">StartQubits musi znajdować się w stanie $ \ket{0 \cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="2640e-113">The startQubits must be in the $\ket{0 \cdots 0}$ state.</span></span> <span data-ttu-id="2640e-114">Ta operacja wykonuje iterację na wielu zapytaniach w uprawnieniach $2 $ do momentu osiągnięcia maksymalnej liczby zapytań lub znalezienia stanu docelowego.</span><span class="sxs-lookup"><span data-stu-id="2640e-114">This operation iterates over a number of queries in powers of $2$ until either a maximal number of queries is reached, or the target state is found.</span></span>