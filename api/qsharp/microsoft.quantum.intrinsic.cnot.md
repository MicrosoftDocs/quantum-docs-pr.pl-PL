---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722670"
---
# <a name="cnot-operation"></a><span data-ttu-id="209f7-102">CNOT, operacja</span><span class="sxs-lookup"><span data-stu-id="209f7-102">CNOT operation</span></span>

<span data-ttu-id="209f7-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="209f7-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="209f7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="209f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="209f7-105">Stosuje bramę sterowaną niezależną (CNOT) do pary qubits.</span><span class="sxs-lookup"><span data-stu-id="209f7-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="209f7-106">\begin{align} \operatorname{CNOT} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 \\ \\ & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="209f7-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="209f7-107">gdzie wiersze i kolumny są uporządkowane jak w przewodniku koncepcji Quantum.</span><span class="sxs-lookup"><span data-stu-id="209f7-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="209f7-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="209f7-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="209f7-109">Kontrolka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="209f7-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="209f7-110">Kontrolka qubit dla bramy CNOT.</span><span class="sxs-lookup"><span data-stu-id="209f7-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="209f7-111">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="209f7-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="209f7-112">Docelowa qubit dla bramy CNOT.</span><span class="sxs-lookup"><span data-stu-id="209f7-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="209f7-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="209f7-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="209f7-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="209f7-114">Remarks</span></span>

<span data-ttu-id="209f7-115">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="209f7-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```