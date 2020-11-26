---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 5f6e3ea1e7638d3bc446f21ace2968cf8284353a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210475"
---
# <a name="prepareentangledstate-operation"></a><span data-ttu-id="e9e57-102">PrepareEntangledState, operacja</span><span class="sxs-lookup"><span data-stu-id="e9e57-102">PrepareEntangledState operation</span></span>

<span data-ttu-id="e9e57-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="e9e57-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="e9e57-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9e57-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9e57-105">Buforowanie entangles dwóch qubit rejestrów.</span><span class="sxs-lookup"><span data-stu-id="e9e57-105">Pairwise entangles two qubit registers.</span></span>

<span data-ttu-id="e9e57-106">W odniesieniu do dwóch rejestrów przygotowuje Maximally Entangled State $ \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right) $ między każdą parą qubits w odpowiednich rejestrach, przy założeniu, że każda Rejestracja zaczyna się w stanie $ \ket{0\cdots 0} $.</span><span class="sxs-lookup"><span data-stu-id="e9e57-106">That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.</span></span>

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="e9e57-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e9e57-107">Input</span></span>

### <a name="left--qubit"></a><span data-ttu-id="e9e57-108">Left: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9e57-108">left : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9e57-109">Tablica qubit w stanie $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="e9e57-109">A qubit array in the $\ket{0\cdots 0}$ state</span></span>


### <a name="right--qubit"></a><span data-ttu-id="e9e57-110">Right: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="e9e57-110">right : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="e9e57-111">Tablica qubit w stanie $ \ket{0\cdots 0} $</span><span class="sxs-lookup"><span data-stu-id="e9e57-111">A qubit array in the $\ket{0\cdots 0}$ state</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9e57-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9e57-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

