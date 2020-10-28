---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerClusterOperatorPQRSTerm
title: Operacja _ApplyJordanWignerClusterOperatorPQRSTerm
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerClusterOperatorPQRSTerm
qsharp.summary: Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.
ms.openlocfilehash: 9f5cd58747b16d3fc755c202fd905394fc221d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714807"
---
# <a name="_applyjordanwignerclusteroperatorpqrsterm-operation"></a><span data-ttu-id="26420-102">Operacja _ApplyJordanWignerClusterOperatorPQRSTerm</span><span class="sxs-lookup"><span data-stu-id="26420-102">_ApplyJordanWignerClusterOperatorPQRSTerm operation</span></span>

<span data-ttu-id="26420-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="26420-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="26420-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26420-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26420-105">Stosuje ewolucję czasową przez operator klastra PQRS termin opisany przez `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="26420-105">Applies time-evolution by a cluster operator PQRS term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerClusterOperatorPQRSTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="26420-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="26420-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="26420-107">termin: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="26420-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="26420-108">`GeneratorIndex` reprezentujący termin PQRS operatora klastra.</span><span class="sxs-lookup"><span data-stu-id="26420-108">`GeneratorIndex` representing a cluster operator PQRS term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="26420-109">stepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="26420-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="26420-110">Czas trwania ewolucji.</span><span class="sxs-lookup"><span data-stu-id="26420-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="26420-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="26420-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="26420-112">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="26420-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="26420-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="26420-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

