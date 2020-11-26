---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledC
title: ApplyMultiControlledC, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledC
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 2d5703eed3a3b6e611ae7c993febf018fcb148b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218414"
---
# <a name="applymulticontrolledc-operation"></a><span data-ttu-id="91673-102">ApplyMultiControlledC, operacja</span><span class="sxs-lookup"><span data-stu-id="91673-102">ApplyMultiControlledC operation</span></span>

<span data-ttu-id="91673-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91673-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91673-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91673-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91673-105">Stosuje mnożenie kontrolowanej wersji operacji pojedynczo kontrolowanej.</span><span class="sxs-lookup"><span data-stu-id="91673-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="91673-106">Modyfikator `C` wskazuje, że operacje pojedynczej qubit są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="91673-106">The modifier `C` indicates that the single-qubit operation is controllable.</span></span>

```qsharp
operation ApplyMultiControlledC (singlyControlledOp : (Qubit[] => Unit), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="91673-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="91673-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit"></a><span data-ttu-id="91673-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="91673-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="91673-109">Operacja kontrolowana przy użyciu jednej qubit.</span><span class="sxs-lookup"><span data-stu-id="91673-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="91673-110">Pierwszy qubit w argumencie operacji przyjmuje się, że jest formantem, a reszta przyjmuje wartość Target qubits.</span><span class="sxs-lookup"><span data-stu-id="91673-110">The first qubit in the argument of the operation is assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="91673-111">`ApplyMultiControlled` zawsze wywołuje `singlyControlledOp` z argumentem o długości co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="91673-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="91673-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="91673-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="91673-113">Kontrolowana Brama nie może być używana do celów konstrukcyjnych.</span><span class="sxs-lookup"><span data-stu-id="91673-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="91673-114">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="91673-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="91673-115">Qubits, które `singlyControlledOp` mają być kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="91673-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="91673-116">Długość `controls` musi być równa co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="91673-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="91673-117">elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="91673-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="91673-118">Docelowy qubits, na którym `singlyControlledOp` działa.</span><span class="sxs-lookup"><span data-stu-id="91673-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91673-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91673-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="91673-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="91673-120">Remarks</span></span>

<span data-ttu-id="91673-121">Ta operacja używa tylko czystego Ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="91673-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="91673-122">Aby uzyskać informacje na temat diagramu wyjaśnień i obwodów, zobacz rysunek 4,10, sekcja 4,3 w Nielsen & Czuang</span><span class="sxs-lookup"><span data-stu-id="91673-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="91673-123">Odwołania</span><span class="sxs-lookup"><span data-stu-id="91673-123">References</span></span>

- [<span data-ttu-id="91673-124">*Michael a. Nielsen, Tomasz L. Czuang*, obliczenia Quantum i informacje o Quantum</span><span class="sxs-lookup"><span data-stu-id="91673-124"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="91673-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="91673-125">See Also</span></span>

- [<span data-ttu-id="91673-126">Microsoft. Quantum. Canon. ApplyMultiControlledCA</span><span class="sxs-lookup"><span data-stu-id="91673-126">Microsoft.Quantum.Canon.ApplyMultiControlledCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledCA)