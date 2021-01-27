---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE._prepareTrialStateWrapper
title: Operacja _prepareTrialStateWrapper
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: _prepareTrialStateWrapper
qsharp.summary: Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint. EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.
ms.openlocfilehash: f0deba39d834731fd9057a1d40d0c78b2b7e6bb8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850216"
---
# <a name="_preparetrialstatewrapper-operation"></a><span data-ttu-id="5eebb-102">Operacja _prepareTrialStateWrapper</span><span class="sxs-lookup"><span data-stu-id="5eebb-102">_prepareTrialStateWrapper operation</span></span>

<span data-ttu-id="5eebb-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="5eebb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="5eebb-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5eebb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5eebb-105">Prywatna otoka dookoła PrepareTrialState, aby była zgodna z EstimateFrequencyA przez zdefiniowanie sąsiedniej.</span><span class="sxs-lookup"><span data-stu-id="5eebb-105">Private wrapper around PrepareTrialState to make it compatible with EstimateFrequencyA by defining an adjoint.</span></span>
<span data-ttu-id="5eebb-106">EstimateFrequencyA ma wbudowaną funkcję emulacji w przypadku kierowania QuantumSimulator, co przyspiesza jego wykonywanie.</span><span class="sxs-lookup"><span data-stu-id="5eebb-106">EstimateFrequencyA has built-in emulation feature when targeting the QuantumSimulator, which speeds up its execution.</span></span>

```qsharp
operation _prepareTrialStateWrapper (inputState : (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), qubits : Qubit[]) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="5eebb-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5eebb-107">Input</span></span>

### <a name="inputstate--intjordanwignerinputstate"></a><span data-ttu-id="5eebb-108">inputState: ([int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span><span class="sxs-lookup"><span data-stu-id="5eebb-108">inputState : ([Int](xref:microsoft.quantum.lang-ref.int),[JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[])</span></span>

<span data-ttu-id="5eebb-109">Jordan-Wigner dane wejściowe wymagane do uruchomienia usługi PrepareTrialState.</span><span class="sxs-lookup"><span data-stu-id="5eebb-109">The Jordan-Wigner input required for PrepareTrialState to run.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5eebb-110">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5eebb-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5eebb-111">Rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="5eebb-111">A qubit register.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5eebb-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5eebb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

