---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZZTerm_
title: _ApplyJordanWignerZZTerm_ , operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZZTerm_
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 9f03255d53f7ed7f3e79689ea53c8b95133f6cde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714723"
---
# <a name="_applyjordanwignerzzterm_-operation"></a><span data-ttu-id="50a45-102">_ApplyJordanWignerZZTerm_ , operacja</span><span class="sxs-lookup"><span data-stu-id="50a45-102">_ApplyJordanWignerZZTerm_ operation</span></span>

<span data-ttu-id="50a45-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="50a45-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="50a45-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50a45-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50a45-105">Stosuje ewolucję czasową przez ZZ termin opisany przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="50a45-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="50a45-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="50a45-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="50a45-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="50a45-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="50a45-108">`GeneratorIndex` reprezentujący termin ZZ.</span><span class="sxs-lookup"><span data-stu-id="50a45-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="50a45-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="50a45-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="50a45-110">Czas trwania ewolucji.</span><span class="sxs-lookup"><span data-stu-id="50a45-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="50a45-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="50a45-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="50a45-112">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="50a45-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="50a45-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="50a45-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

