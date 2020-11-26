---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: PreparePauliEigenstate, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193696"
---
# <a name="preparepaulieigenstate-operation"></a><span data-ttu-id="efba2-102">PreparePauliEigenstate, operacja</span><span class="sxs-lookup"><span data-stu-id="efba2-102">PreparePauliEigenstate operation</span></span>

<span data-ttu-id="efba2-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="efba2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="efba2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="efba2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="efba2-105">Przygotowuje element qubit do pozytywnej eigenstatea danego operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="efba2-105">Prepares a qubit in the positive eigenstate of a given Pauli operator.</span></span>
<span data-ttu-id="efba2-106">Jeśli jest określony operator Identity, qubit jest przygotowana w stanie mieszanym Maximally.</span><span class="sxs-lookup"><span data-stu-id="efba2-106">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="efba2-107">Opis</span><span class="sxs-lookup"><span data-stu-id="efba2-107">Description</span></span>

<span data-ttu-id="efba2-108">Jeśli qubit był początkowo w stanie $ \ket {0} $, ta operacja przygotowuje qubit w eigenstate $ + $1 danego operatora Pauli lub, dla `PauliI` , w stanie mieszanym Maximally (zobacz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="efba2-108">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="efba2-109">Jeśli qubit było w stanie innym niż $ \ket {0} $, ta operacja stosuje następujące bramy: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ dla `PauliZ` i <xref:microsoft.quantum.preparation.preparesinglequbitidentity> dla `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="efba2-109">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

## <a name="input"></a><span data-ttu-id="efba2-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="efba2-110">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="efba2-111">Podstawa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="efba2-111">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="efba2-112">Operator Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="efba2-112">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="efba2-113">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="efba2-113">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="efba2-114">Qubit do przygotowania.</span><span class="sxs-lookup"><span data-stu-id="efba2-114">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="efba2-115">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="efba2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

