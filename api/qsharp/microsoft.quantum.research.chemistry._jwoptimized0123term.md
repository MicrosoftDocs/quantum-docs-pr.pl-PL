---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimized0123Term
title: Operacja _JWOptimized0123Term
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimized0123Term
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 8b304ee99bf4ebfbe925285df9ee6a60775c86c4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845988"
---
# <a name="_jwoptimized0123term-operation"></a><span data-ttu-id="4100a-102">Operacja _JWOptimized0123Term</span><span class="sxs-lookup"><span data-stu-id="4100a-102">_JWOptimized0123Term operation</span></span>

<span data-ttu-id="4100a-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4100a-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="4100a-104">Pakiet: [Microsoft. Quantum. Research. Chemia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4100a-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="4100a-105">Stosuje ewolucję czasową przez PQRS termin opisany przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="4100a-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimized0123Term (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4100a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4100a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="4100a-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4100a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4100a-108">`GeneratorIndex` reprezentujący termin PQRS.</span><span class="sxs-lookup"><span data-stu-id="4100a-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="4100a-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4100a-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4100a-110">Czas trwania ewolucji.</span><span class="sxs-lookup"><span data-stu-id="4100a-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="4100a-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4100a-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4100a-112">Qubit, który określa znak ewolucji czasu.</span><span class="sxs-lookup"><span data-stu-id="4100a-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4100a-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4100a-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4100a-114">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="4100a-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4100a-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4100a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

