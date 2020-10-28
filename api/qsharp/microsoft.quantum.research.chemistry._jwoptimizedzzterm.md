---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: Operacja _JWOptimizedZZTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 824918e06e54e31834019a396b310bbaa6beeb46
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722777"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="2650a-102">Operacja _JWOptimizedZZTerm</span><span class="sxs-lookup"><span data-stu-id="2650a-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="2650a-103">Przestrzeń nazw: [Microsoft. Quantum. Research. Chemia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2650a-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="2650a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2650a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2650a-105">Stosuje ewolucję czasową przez ZZ termin opisany przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="2650a-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2650a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2650a-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="2650a-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="2650a-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="2650a-108">`GeneratorIndex` reprezentujący termin ZZ.</span><span class="sxs-lookup"><span data-stu-id="2650a-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="2650a-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2650a-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2650a-110">Czas trwania ewolucji.</span><span class="sxs-lookup"><span data-stu-id="2650a-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="2650a-111">parityQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2650a-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2650a-112">Qubit, który określa znak ewolucji czasu.</span><span class="sxs-lookup"><span data-stu-id="2650a-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="2650a-113">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2650a-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2650a-114">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="2650a-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2650a-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2650a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

