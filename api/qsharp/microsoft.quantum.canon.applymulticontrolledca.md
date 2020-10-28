---
uid: Microsoft.Quantum.Canon.ApplyMultiControlledCA
title: ApplyMultiControlledCA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiControlledCA
qsharp.summary: Applies a multiply controlled version of a singly controlled operation. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: 5662efe0dc6f665206b8773596bf885ce631413c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717962"
---
# <a name="applymulticontrolledca-operation"></a><span data-ttu-id="b07fc-102">ApplyMultiControlledCA, operacja</span><span class="sxs-lookup"><span data-stu-id="b07fc-102">ApplyMultiControlledCA operation</span></span>

<span data-ttu-id="b07fc-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b07fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b07fc-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b07fc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b07fc-105">Stosuje mnożenie kontrolowanej wersji operacji pojedynczo kontrolowanej.</span><span class="sxs-lookup"><span data-stu-id="b07fc-105">Applies a multiply controlled version of a singly controlled operation.</span></span>
<span data-ttu-id="b07fc-106">Modyfikator `CA` wskazuje, że operacje pojedynczego qubit są kontrolowane i sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="b07fc-106">The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.</span></span>

```qsharp
operation ApplyMultiControlledCA (singlyControlledOp : (Qubit[] => Unit is Adj), ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="b07fc-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b07fc-107">Input</span></span>

### <a name="singlycontrolledop--qubit--unit-adj"></a><span data-ttu-id="b07fc-108">singlyControlledOp: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b07fc-108">singlyControlledOp : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="b07fc-109">Operacja kontrolowana przy użyciu jednej qubit.</span><span class="sxs-lookup"><span data-stu-id="b07fc-109">An operation controlled on a single qubit.</span></span>
<span data-ttu-id="b07fc-110">Pierwszy qubit w argumencie operacji założono, że jest formantem, a reszta przyjmuje wartość Target qubits.</span><span class="sxs-lookup"><span data-stu-id="b07fc-110">The first qubit in the argument of the operation assumed to be a control and the rest are assumed to be target qubits.</span></span>
<span data-ttu-id="b07fc-111">`ApplyMultiControlled` zawsze wywołuje `singlyControlledOp` z argumentem o długości co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="b07fc-111">`ApplyMultiControlled` always calls `singlyControlledOp` with an argument of length at least 1.</span></span>


### <a name="ccnot--ccnotop"></a><span data-ttu-id="b07fc-112">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="b07fc-112">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="b07fc-113">Kontrolowana Brama nie może być używana do celów konstrukcyjnych.</span><span class="sxs-lookup"><span data-stu-id="b07fc-113">The controlled-controlled-NOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="b07fc-114">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b07fc-114">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b07fc-115">Qubits, które `singlyControlledOp` mają być kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="b07fc-115">The qubits that `singlyControlledOp` is to be controlled on.</span></span>
<span data-ttu-id="b07fc-116">Długość `controls` musi być równa co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="b07fc-116">The length of `controls` must be at least 1.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="b07fc-117">elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b07fc-117">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b07fc-118">Docelowy qubits, na którym `singlyControlledOp` działa.</span><span class="sxs-lookup"><span data-stu-id="b07fc-118">The target qubits that `singlyControlledOp` acts upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b07fc-119">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b07fc-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b07fc-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b07fc-120">Remarks</span></span>

<span data-ttu-id="b07fc-121">Ta operacja używa tylko czystego Ancilla qubits.</span><span class="sxs-lookup"><span data-stu-id="b07fc-121">This operation uses only clean ancilla qubits.</span></span>

<span data-ttu-id="b07fc-122">Aby uzyskać informacje na temat diagramu wyjaśnień i obwodów, zobacz rysunek 4,10, sekcja 4,3 w Nielsen & Czuang</span><span class="sxs-lookup"><span data-stu-id="b07fc-122">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang</span></span>

## <a name="references"></a><span data-ttu-id="b07fc-123">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="b07fc-123">References</span></span>

- [<span data-ttu-id="b07fc-124">*Michael a. Nielsen, Tomasz L. Czuang* , obliczenia Quantum i informacje o Quantum</span><span class="sxs-lookup"><span data-stu-id="b07fc-124"> *Michael A. Nielsen , Isaac L. Chuang* , Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)

## <a name="see-also"></a><span data-ttu-id="b07fc-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b07fc-125">See Also</span></span>

- [<span data-ttu-id="b07fc-126">Microsoft. Quantum. Canon. ApplyMultiControlledC</span><span class="sxs-lookup"><span data-stu-id="b07fc-126">Microsoft.Quantum.Canon.ApplyMultiControlledC</span></span>](xref:Microsoft.Quantum.Canon.ApplyMultiControlledC)