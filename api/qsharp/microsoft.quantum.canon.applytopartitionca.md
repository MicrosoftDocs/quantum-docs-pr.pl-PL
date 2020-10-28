---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: ApplyToPartitionCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 8ea437a0e25ed43eb745a7740ecd8861ced1350a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717122"
---
# <a name="applytopartitionca-operation"></a><span data-ttu-id="ec9ac-102">ApplyToPartitionCA, operacja</span><span class="sxs-lookup"><span data-stu-id="ec9ac-102">ApplyToPartitionCA operation</span></span>

<span data-ttu-id="ec9ac-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec9ac-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec9ac-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec9ac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec9ac-105">Stosuje parę operacji do danej partycji rejestracji w dwóch częściach.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="ec9ac-106">Modyfikator `CA` wskazuje, że operacja jest sterowana i sąsiadująca.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-106">The modifier `CA` indicates that the operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ec9ac-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ec9ac-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl--adj"></a><span data-ttu-id="ec9ac-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik</span><span class="sxs-lookup"><span data-stu-id="ec9ac-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="ec9ac-109">Para operacji do zastosowania do danej partycji.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="ec9ac-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ec9ac-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ec9ac-111">Liczba qubits z elementu docelowego, które mają zostać umieszczone w pierwszej części partycji.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="ec9ac-112">Pozostałe qubits stanowią drugą część partycji.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ec9ac-113">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ec9ac-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ec9ac-114">Rejestr qubits, które są partycjonowane i obsługiwane przez daną dwie operacje.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec9ac-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec9ac-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="ec9ac-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ec9ac-116">See Also</span></span>

- [<span data-ttu-id="ec9ac-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="ec9ac-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)