---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: _ApplyJordanWignerZTerm_ , operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: c27255409061a28668270d69133fbccb6b01b493
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839552"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="ad4ee-102">_ApplyJordanWignerZTerm_ , operacja</span><span class="sxs-lookup"><span data-stu-id="ad4ee-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="ad4ee-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ad4ee-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ad4ee-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ad4ee-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ad4ee-105">Stosuje ewolucję czasową z terminem Z opisanym przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ad4ee-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="ad4ee-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ad4ee-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="ad4ee-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ad4ee-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ad4ee-108">`GeneratorIndex` reprezentujący okres Z.</span><span class="sxs-lookup"><span data-stu-id="ad4ee-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ad4ee-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ad4ee-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ad4ee-110">Czas trwania ewolucji.</span><span class="sxs-lookup"><span data-stu-id="ad4ee-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ad4ee-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ad4ee-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ad4ee-112">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="ad4ee-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ad4ee-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ad4ee-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

