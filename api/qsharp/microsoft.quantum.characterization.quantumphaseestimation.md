---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839661"
---
# <a name="quantumphaseestimation-operation"></a><span data-ttu-id="6cc36-102">QuantumPhaseEstimation, operacja</span><span class="sxs-lookup"><span data-stu-id="6cc36-102">QuantumPhaseEstimation operation</span></span>

<span data-ttu-id="6cc36-103">Przestrzeń nazw: [Microsoft. Quantum. charakteryzującą](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="6cc36-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="6cc36-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6cc36-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6cc36-105">Wykonuje algorytm szacowania fazy Quantum dla danego programu Oracle `U` i `targetState` odczytuje fazę do rejestru Quantum big-endian.</span><span class="sxs-lookup"><span data-stu-id="6cc36-105">Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.</span></span>

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6cc36-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6cc36-106">Input</span></span>

### <a name="oracle--discreteoracle"></a><span data-ttu-id="6cc36-107">Oracle: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="6cc36-107">oracle : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="6cc36-108">Operacja implementująca $U ^ m $ dla podaną liczbę całkowitą potęgi m.</span><span class="sxs-lookup"><span data-stu-id="6cc36-108">An operation implementing $U^m$ for given integer powers m.</span></span>


### <a name="targetstate--qubit"></a><span data-ttu-id="6cc36-109">targetState: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6cc36-109">targetState : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6cc36-110">Rejestr Quantum reprezentujący stan $ \ket{\phi} $ działał na $U $.</span><span class="sxs-lookup"><span data-stu-id="6cc36-110">A quantum register representing the state $\ket{\phi}$ acted on by $U$.</span></span> <span data-ttu-id="6cc36-111">Jeśli $ \ket{\phi} $ jest eigenstateem $U $, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ dla $ \phi \In [0, 2 \ PI) $ nieznana faza.</span><span class="sxs-lookup"><span data-stu-id="6cc36-111">If $\ket{\phi}$ is an eigenstate of $U$, $U\ket{\phi} = e^{i\phi} \ket{\phi}$ for $\phi \in [0, 2\pi)$ an unknown phase.</span></span>


### <a name="controlregister--bigendian"></a><span data-ttu-id="6cc36-112">controlRegister: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="6cc36-112">controlRegister : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="6cc36-113">Rejestr operacji big-endian, który może służyć do kontrolowania dostarczonej firmy Oracle i który będzie zawierać reprezentację $ \phi $ po zastosowaniu tej operacji.</span><span class="sxs-lookup"><span data-stu-id="6cc36-113">A big-endian representation integer register that can be used to control the provided oracle, and that will contain the a representation of $\phi$ following the application of this operation.</span></span> <span data-ttu-id="6cc36-114">Założono, że controlRegister rozpoczyna się w stanie początkowym $ \ket{00\cdots 0} $, gdzie długość rejestru wskazuje żądaną precyzję.</span><span class="sxs-lookup"><span data-stu-id="6cc36-114">The controlRegister is assumed to start in the initial state $\ket{00\cdots 0}$, where the length of the register indicates the desired precision.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6cc36-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6cc36-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

