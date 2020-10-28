---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: ApplyToPartition, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: c1f43e7936fc1c18fb665388e9892dc3b74cdd05
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717145"
---
# <a name="applytopartition-operation"></a><span data-ttu-id="9903f-102">ApplyToPartition, operacja</span><span class="sxs-lookup"><span data-stu-id="9903f-102">ApplyToPartition operation</span></span>

<span data-ttu-id="9903f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9903f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9903f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9903f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9903f-105">Stosuje parę operacji do danej partycji rejestracji w dwóch częściach.</span><span class="sxs-lookup"><span data-stu-id="9903f-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="9903f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9903f-106">Input</span></span>

### <a name="op--qubitqubit--unit"></a><span data-ttu-id="9903f-107">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="9903f-107">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9903f-108">Para operacji do zastosowania do danej partycji.</span><span class="sxs-lookup"><span data-stu-id="9903f-108">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="9903f-109">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9903f-109">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9903f-110">Liczba qubits z elementu docelowego, które mają zostać umieszczone w pierwszej części partycji.</span><span class="sxs-lookup"><span data-stu-id="9903f-110">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="9903f-111">Pozostałe qubits stanowią drugą część partycji.</span><span class="sxs-lookup"><span data-stu-id="9903f-111">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9903f-112">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9903f-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9903f-113">Rejestr qubits, które są partycjonowane i obsługiwane przez daną dwie operacje.</span><span class="sxs-lookup"><span data-stu-id="9903f-113">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9903f-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9903f-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="9903f-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9903f-115">See Also</span></span>

- [<span data-ttu-id="9903f-116">Microsoft. Quantum. Canon. ApplyToPartitionA</span><span class="sxs-lookup"><span data-stu-id="9903f-116">Microsoft.Quantum.Canon.ApplyToPartitionA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [<span data-ttu-id="9903f-117">Microsoft. Quantum. Canon. ApplyToPartitionC</span><span class="sxs-lookup"><span data-stu-id="9903f-117">Microsoft.Quantum.Canon.ApplyToPartitionC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [<span data-ttu-id="9903f-118">Microsoft. Quantum. Canon. ApplyToPartitionCA</span><span class="sxs-lookup"><span data-stu-id="9903f-118">Microsoft.Quantum.Canon.ApplyToPartitionCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)