---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718365"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="b63fa-102">ApplyCNOTChainWithTarget, operacja</span><span class="sxs-lookup"><span data-stu-id="b63fa-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="b63fa-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b63fa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b63fa-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b63fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b63fa-105">Oblicza parzystość tablicy qubits w docelowym qubit.</span><span class="sxs-lookup"><span data-stu-id="b63fa-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="b63fa-106">Opis</span><span class="sxs-lookup"><span data-stu-id="b63fa-106">Description</span></span>

<span data-ttu-id="b63fa-107">Jeśli tablica jest początkowo w stanie $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\Text{Target}}} $, stan końcowy jest określony przez $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\Text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="b63fa-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="b63fa-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b63fa-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="b63fa-109">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b63fa-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b63fa-110">Tablica qubits, w której jest obliczana parzystość.</span><span class="sxs-lookup"><span data-stu-id="b63fa-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="b63fa-111">targetQubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b63fa-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b63fa-112">Końcowa qubit, do której parzystość elementu "qubits" to XORed.</span><span class="sxs-lookup"><span data-stu-id="b63fa-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b63fa-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b63fa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b63fa-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b63fa-114">Remarks</span></span>

<span data-ttu-id="b63fa-115">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="b63fa-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="b63fa-116">oraz</span><span class="sxs-lookup"><span data-stu-id="b63fa-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```