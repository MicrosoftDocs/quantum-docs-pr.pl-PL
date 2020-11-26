---
uid: Microsoft.Quantum.Diagnostics._flipToBasis
title: Operacja _flipToBasis
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _flipToBasis
qsharp.summary: >-
  Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.

  The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:

  - `basis[k]=0` $\rightarrow \ket{0}$. - `basis[k]=1` $\rightarrow \ket{1}$. - `basis[k]=2` $\rightarrow \ket{+}$. - `basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).
ms.openlocfilehash: 1581a1267902ceee81d6f01348f4ee718e49ee47
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223990"
---
# <a name="_fliptobasis-operation"></a><span data-ttu-id="6a409-102">Operacja _flipToBasis</span><span class="sxs-lookup"><span data-stu-id="6a409-102">_flipToBasis operation</span></span>

<span data-ttu-id="6a409-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6a409-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6a409-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6a409-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6a409-105">Stosuje unitaries, które mapują $ \ket {0} \otimes\cdots\ket {0} $ do $ \ket{\ psi_0} \otimes \ket{\ psi_ {n-1}} $, w której zależy $ \ket{\ psi_k} $ `basis[k]` .</span><span class="sxs-lookup"><span data-stu-id="6a409-105">Applies unitaries that map $\ket{0}\otimes\cdots\ket{0}$ to $\ket{\psi_0} \otimes \ket{\psi_{n - 1}}$, where $\ket{\psi_k}$ depends on `basis[k]`.</span></span>

<span data-ttu-id="6a409-106">Zgodność między wartością `basis[k]` i $ \ket{\ psi_k} $ jest następująca:</span><span class="sxs-lookup"><span data-stu-id="6a409-106">The correspondence between value of `basis[k]` and $\ket{\psi_k}$ is the following:</span></span>

- <span data-ttu-id="6a409-107">`basis[k]=0` $ \rightarrow \ket {0} $.</span><span class="sxs-lookup"><span data-stu-id="6a409-107">`basis[k]=0` $\rightarrow \ket{0}$.</span></span>
- <span data-ttu-id="6a409-108">`basis[k]=1` $ \rightarrow \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="6a409-108">`basis[k]=1` $\rightarrow \ket{1}$.</span></span>
- <span data-ttu-id="6a409-109">`basis[k]=2` $ \rightarrow \ket{+} $.</span><span class="sxs-lookup"><span data-stu-id="6a409-109">`basis[k]=2` $\rightarrow \ket{+}$.</span></span>
- <span data-ttu-id="6a409-110">`basis[k]=3` $ \rightarrow \ket{i} $ (+ 1 eigenstate of Pauli Y).</span><span class="sxs-lookup"><span data-stu-id="6a409-110">`basis[k]=3` $\rightarrow \ket{i}$ ( +1 eigenstate of Pauli Y ).</span></span>

```qsharp
operation _flipToBasis (basis : Int[], qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6a409-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6a409-111">Input</span></span>

### <a name="basis--int"></a><span data-ttu-id="6a409-112">Podstawa: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6a409-112">basis : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6a409-113">Tablica identyfikatorów stanu podstawowe qubit (0 <= ID <= 3), jeden dla każdego elementu qubits.</span><span class="sxs-lookup"><span data-stu-id="6a409-113">Array of single-qubit basis state IDs (0 <= id <= 3), one for each element of qubits.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6a409-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6a409-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6a409-115">Qubit.</span><span class="sxs-lookup"><span data-stu-id="6a409-115">Qubit to be operated on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6a409-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6a409-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

