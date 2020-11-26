---
uid: Microsoft.Quantum.Chemistry.JordanWigner.PrepareSingleConfigurationalStateSingleSiteOccupation
title: PrepareSingleConfigurationalStateSingleSiteOccupation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: PrepareSingleConfigurationalStateSingleSiteOccupation
qsharp.summary: Simple state preparation of trial state by occupying spin-orbitals
ms.openlocfilehash: 360800037318f56d0bb659aeb2a2c6292f860b2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214555"
---
# <a name="preparesingleconfigurationalstatesinglesiteoccupation-operation"></a><span data-ttu-id="5f9b8-102">PrepareSingleConfigurationalStateSingleSiteOccupation, operacja</span><span class="sxs-lookup"><span data-stu-id="5f9b8-102">PrepareSingleConfigurationalStateSingleSiteOccupation operation</span></span>

<span data-ttu-id="5f9b8-103">Przestrzeń nazw: [Microsoft. Quantum. Chemia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="5f9b8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="5f9b8-104">Pakiet: [Microsoft. Quantum. Chemia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="5f9b8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="5f9b8-105">Proste przygotowanie stanu wersji próbnej przez zajmowanie orbitals</span><span class="sxs-lookup"><span data-stu-id="5f9b8-105">Simple state preparation of trial state by occupying spin-orbitals</span></span>

```qsharp
operation PrepareSingleConfigurationalStateSingleSiteOccupation (qubitIndices : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5f9b8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5f9b8-106">Input</span></span>

### <a name="qubitindices--int"></a><span data-ttu-id="5f9b8-107">qubitIndices: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5f9b8-107">qubitIndices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5f9b8-108">Indeksy qubits są zajęte przez Electrons.</span><span class="sxs-lookup"><span data-stu-id="5f9b8-108">Indices of qubits to be occupied by electrons.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5f9b8-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5f9b8-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5f9b8-110">Qubits hamiltonian.</span><span class="sxs-lookup"><span data-stu-id="5f9b8-110">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5f9b8-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5f9b8-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

