---
uid: Microsoft.Quantum.Canon.ApplyToPartitionC
title: ApplyToPartitionC, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionC
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 840c93c653d71af1a82fb0dc51d9e056176ba88b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717117"
---
# <a name="applytopartitionc-operation"></a><span data-ttu-id="c6568-102">ApplyToPartitionC, operacja</span><span class="sxs-lookup"><span data-stu-id="c6568-102">ApplyToPartitionC operation</span></span>

<span data-ttu-id="c6568-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c6568-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c6568-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c6568-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c6568-105">Stosuje parę operacji do danej partycji rejestracji w dwóch częściach.</span><span class="sxs-lookup"><span data-stu-id="c6568-105">Applies a pair of operations to a given partition of a register into two parts.</span></span>
<span data-ttu-id="c6568-106">Modyfikator `C` wskazuje, że operacja jest sterowana.</span><span class="sxs-lookup"><span data-stu-id="c6568-106">The modifier `C` indicates that the operation is controllable.</span></span>

```qsharp
operation ApplyToPartitionC (op : ((Qubit[], Qubit[]) => Unit is Ctl), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="c6568-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="c6568-107">Input</span></span>

### <a name="op--qubitqubit--unit-ctl"></a><span data-ttu-id="c6568-108">op: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6568-108">op : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="c6568-109">Para operacji do zastosowania do danej partycji.</span><span class="sxs-lookup"><span data-stu-id="c6568-109">The pair of operations to be applied to the given partition.</span></span>


### <a name="numberofqubitstofirstargument--int"></a><span data-ttu-id="c6568-110">numberOfQubitsToFirstArgument: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c6568-110">numberOfQubitsToFirstArgument : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c6568-111">Liczba qubits z elementu docelowego, które mają zostać umieszczone w pierwszej części partycji.</span><span class="sxs-lookup"><span data-stu-id="c6568-111">Number of qubits from target to put into the first part of the partition.</span></span>
<span data-ttu-id="c6568-112">Pozostałe qubits stanowią drugą część partycji.</span><span class="sxs-lookup"><span data-stu-id="c6568-112">The remaining qubits constitute the second part of the partition.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c6568-113">target: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c6568-113">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c6568-114">Rejestr qubits, które są partycjonowane i obsługiwane przez daną dwie operacje.</span><span class="sxs-lookup"><span data-stu-id="c6568-114">A register of qubits that are being partitioned and operated on by the given two operation.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c6568-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c6568-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="c6568-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c6568-116">See Also</span></span>

- [<span data-ttu-id="c6568-117">Microsoft. Quantum. Canon. ApplyToPartition</span><span class="sxs-lookup"><span data-stu-id="c6568-117">Microsoft.Quantum.Canon.ApplyToPartition</span></span>](xref:Microsoft.Quantum.Canon.ApplyToPartition)