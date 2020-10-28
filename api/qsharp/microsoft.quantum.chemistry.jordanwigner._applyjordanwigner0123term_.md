---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWigner0123Term_
title: _ApplyJordanWigner0123Term_ , operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWigner0123Term_
qsharp.summary: Applies time-evolution by a PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 36590b2ee9f6f6c2b5e076f8e334dfe7b0144e5e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714821"
---
# <a name="_applyjordanwigner0123term_-operation"></a><span data-ttu-id="cbeb4-102">_ApplyJordanWigner0123Term_ , operacja</span><span class="sxs-lookup"><span data-stu-id="cbeb4-102">_ApplyJordanWigner0123Term_ operation</span></span>

<span data-ttu-id="cbeb4-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="cbeb4-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="cbeb4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cbeb4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cbeb4-105">Stosuje ewolucję czasową przez PQRS termin opisany przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="cbeb4-105">Applies time-evolution by a PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWigner0123Term_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cbeb4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cbeb4-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="cbeb4-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cbeb4-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cbeb4-108">`GeneratorIndex` reprezentujący termin PQRS.</span><span class="sxs-lookup"><span data-stu-id="cbeb4-108">`GeneratorIndex` representing a PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="cbeb4-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cbeb4-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cbeb4-110">Czas trwania ewolucji.</span><span class="sxs-lookup"><span data-stu-id="cbeb4-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cbeb4-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cbeb4-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cbeb4-112">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="cbeb4-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbeb4-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbeb4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

