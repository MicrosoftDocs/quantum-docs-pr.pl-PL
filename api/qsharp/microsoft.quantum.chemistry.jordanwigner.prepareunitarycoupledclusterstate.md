---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareUnitaryCoupledClusterState
title: PrepareUnitaryCoupledClusterState, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareUnitaryCoupledClusterState
qsharp.summary: Unitary coupled-cluster state preparation of trial state
ms.openlocfilehash: 4db31e3e79d27f12178dbf121cd04727c2332c62
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713827"
---
# <a name="prepareunitarycoupledclusterstate-operation"></a><span data-ttu-id="31a4b-102">PrepareUnitaryCoupledClusterState, operacja</span><span class="sxs-lookup"><span data-stu-id="31a4b-102">PrepareUnitaryCoupledClusterState operation</span></span>

<span data-ttu-id="31a4b-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="31a4b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="31a4b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31a4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31a4b-105">Połączony z jednostką — przygotowanie stanu wersji próbnej dla klastra</span><span class="sxs-lookup"><span data-stu-id="31a4b-105">Unitary coupled-cluster state preparation of trial state</span></span>

```qsharp
operation PrepareUnitaryCoupledClusterState (initialStatePreparation : (Qubit[] => Unit), clusterOperator : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[], trotterStepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="31a4b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="31a4b-106">Input</span></span>

### <a name="initialstatepreparation--qubit--unit"></a><span data-ttu-id="31a4b-107">initialStatePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="31a4b-107">initialStatePreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="31a4b-108">Jednostka przygotowana do przygotowania wstępnego stanu wersji próbnej.</span><span class="sxs-lookup"><span data-stu-id="31a4b-108">Unitary to prepare initial trial state.</span></span>


### <a name="clusteroperator--jordanwignerinputstate"></a><span data-ttu-id="31a4b-109">clusterOperator: [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="31a4b-109">clusterOperator : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>




### <a name="trotterstepsize--double"></a><span data-ttu-id="31a4b-110">trotterStepSize: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="31a4b-110">trotterStepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="qubits--qubit"></a><span data-ttu-id="31a4b-111">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="31a4b-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="31a4b-112">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="31a4b-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="31a4b-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="31a4b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

