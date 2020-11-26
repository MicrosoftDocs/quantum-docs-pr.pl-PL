---
uid: Microsoft.Quantum.Canon.AndLadder
title: AndLadder, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: AndLadder
qsharp.summary: Performs a controlled "AND ladder" on a register of target qubits.
ms.openlocfilehash: 2c6114ec8a5caabdeea8ab7e26a4877e1633671c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209727"
---
# <a name="andladder-operation"></a><span data-ttu-id="0ae7d-102">AndLadder, operacja</span><span class="sxs-lookup"><span data-stu-id="0ae7d-102">AndLadder operation</span></span>

<span data-ttu-id="0ae7d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0ae7d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0ae7d-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0ae7d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0ae7d-105">Wykonuje kontrolowane "i drabinę" w rejestrze docelowej qubits.</span><span class="sxs-lookup"><span data-stu-id="0ae7d-105">Performs a controlled "AND ladder" on a register of target qubits.</span></span>

```qsharp
operation AndLadder (ccnot : Microsoft.Quantum.Canon.CCNOTop, controls : Qubit[], targets : Qubit[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="0ae7d-106">Opis</span><span class="sxs-lookup"><span data-stu-id="0ae7d-106">Description</span></span>

<span data-ttu-id="0ae7d-107">Ta operacja dotyczy transformacji opisanej przez następujące mapowanie podstawy obliczeniowej, $ $ \begin{align} \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1, \dots, y \_ {n-1}} \mapsto \ket{x \_ 1, \dots, x \_ n} \ket{y \_ 1 \oplus (x \_ 1 \land x \_ 2), \dots, y \_ {n-1} \oplus (x \_ 1 \land x \_ 2 \land \cdots \land x \_ {n-1}}, \end{align} $ $ WHERE $ \ket{x \_ 1, \dots, x n} $ odwołuje się do \_ Stanów bazowych `controls` , i gdzie $ \ket{y \_ 1, \dots, y \_ {n-1}} $ odnosi się do Stanów bazowych `targets` .</span><span class="sxs-lookup"><span data-stu-id="0ae7d-107">This operation applies a transformation described by the following mapping of the computational basis, $$ \begin{align} \ket{x\_1, \dots, x\_n} \ket{y\_1, \dots, y\_{n - 1}} \mapsto \ket{x\_1, \dots, x\_n} \ket{ y\_1 \oplus (x\_1 \land x\_2), \dots, y\_{n - 1} \oplus (x\_1 \land x\_2 \land \cdots \land x\_{n - 1} }, \end{align} $$ where $\ket{x\_1, \dots, x\_n}$ refers to the computational basis states of `controls`, and where $\ket{y\_1, \dots, y\_{n - 1}}$ refers to the computational basis states of `targets`.</span></span>

## <a name="input"></a><span data-ttu-id="0ae7d-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0ae7d-108">Input</span></span>

### <a name="ccnot--ccnotop"></a><span data-ttu-id="0ae7d-109">ccnot: [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span><span class="sxs-lookup"><span data-stu-id="0ae7d-109">ccnot : [CCNOTop](xref:Microsoft.Quantum.Canon.CCNOTop)</span></span>

<span data-ttu-id="0ae7d-110">Brama CCNOT do użycia na potrzeby konstruowania.</span><span class="sxs-lookup"><span data-stu-id="0ae7d-110">The CCNOT gate to use for the construction.</span></span>


### <a name="controls--qubit"></a><span data-ttu-id="0ae7d-111">kontrolki: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0ae7d-111">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0ae7d-112">Rejestr qubits, który ma być używany jako kontrolki i Drabinka.</span><span class="sxs-lookup"><span data-stu-id="0ae7d-112">A register of qubits to be used as controls for the and ladder.</span></span>
<span data-ttu-id="0ae7d-113">Ta operacja pozostawia podstawowe Stany `controls` niezmiennej.</span><span class="sxs-lookup"><span data-stu-id="0ae7d-113">This operation leaves computational basis states of `controls` invariant.</span></span>
<span data-ttu-id="0ae7d-114">Długość `controls` musi wynosić co najmniej 2 i musi być równa 1 i długości `targets` .</span><span class="sxs-lookup"><span data-stu-id="0ae7d-114">The length of `controls` must be at least 2, and must be equal to one plus the length of `targets`.</span></span>


### <a name="targets--qubit"></a><span data-ttu-id="0ae7d-115">elementy docelowe: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0ae7d-115">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0ae7d-116">Długość `targets` musi być co najmniej 1 i równa długości `controls` minus jeden.</span><span class="sxs-lookup"><span data-stu-id="0ae7d-116">The length of `targets` must be at least 1 and equal to the length of `controls` minus one.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0ae7d-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0ae7d-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="0ae7d-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0ae7d-118">Remarks</span></span>

- <span data-ttu-id="0ae7d-119">Używane jako część <xref:microsoft.quantum.canon.applymulticontrolledc> i <xref:microsoft.quantum.canon.applymulticontrolledca> .</span><span class="sxs-lookup"><span data-stu-id="0ae7d-119">Used as a part of <xref:microsoft.quantum.canon.applymulticontrolledc> and <xref:microsoft.quantum.canon.applymulticontrolledca>.</span></span>
- <span data-ttu-id="0ae7d-120">Aby uzyskać informacje na temat diagramu wyjaśnień i obwodów, zobacz rysunek 4,10, sekcja 4,3 w Nielsen & Czuang.</span><span class="sxs-lookup"><span data-stu-id="0ae7d-120">For the explanation and circuit diagram see Figure 4.10, Section 4.3 in Nielsen & Chuang.</span></span>

## <a name="references"></a><span data-ttu-id="0ae7d-121">Odwołania</span><span class="sxs-lookup"><span data-stu-id="0ae7d-121">References</span></span>

- [<span data-ttu-id="0ae7d-122">*Michael a. Nielsen, Tomasz L. Czuang*, obliczenia Quantum i informacje o Quantum</span><span class="sxs-lookup"><span data-stu-id="0ae7d-122"> *Michael A. Nielsen , Isaac L. Chuang*, Quantum Computation and Quantum Information </span></span>](http://doi.org/10.1017/CBO9780511976667)