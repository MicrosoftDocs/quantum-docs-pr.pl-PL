---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: PrepareQubit, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  > [!WARNING]

  > PrepareQubit has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.


  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 84674d70d6a038ceaf1c637b22afa1b724d90795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193526"
---
# <a name="preparequbit-operation"></a><span data-ttu-id="8ad6e-102">PrepareQubit, operacja</span><span class="sxs-lookup"><span data-stu-id="8ad6e-102">PrepareQubit operation</span></span>

<span data-ttu-id="8ad6e-103">Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="8ad6e-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="8ad6e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8ad6e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="8ad6e-105">PrepareQubit jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="8ad6e-105">PrepareQubit has been deprecated.</span></span> <span data-ttu-id="8ad6e-106">Użyj <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> zamiast tego.</span><span class="sxs-lookup"><span data-stu-id="8ad6e-106">Please use <xref:Microsoft.Quantum.Preparation.PreparePauliEigenstate> instead.</span></span>

<span data-ttu-id="8ad6e-107">Przygotowuje qubit w + 1 ( `Zero` ) eigenstate danego operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="8ad6e-107">Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator.</span></span>
<span data-ttu-id="8ad6e-108">Jeśli jest określony operator Identity, qubit jest przygotowana w stanie mieszanym Maximally.</span><span class="sxs-lookup"><span data-stu-id="8ad6e-108">If the identity operator is given, then the qubit is prepared in the maximally mixed state.</span></span>

<span data-ttu-id="8ad6e-109">Jeśli qubit był początkowo w stanie $ \ket {0} $, ta operacja przygotowuje qubit w eigenstate $ + $1 danego operatora Pauli lub, dla `PauliI` , w stanie mieszanym Maximally (zobacz <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).</span><span class="sxs-lookup"><span data-stu-id="8ad6e-109">If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).</span></span>

<span data-ttu-id="8ad6e-110">Jeśli qubit było w stanie innym niż $ \ket {0} $, ta operacja stosuje następujące bramy: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ dla `PauliZ` i <xref:microsoft.quantum.preparation.preparesinglequbitidentity> dla `PauliI` .</span><span class="sxs-lookup"><span data-stu-id="8ad6e-110">If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.</span></span>

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="8ad6e-111">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8ad6e-111">Input</span></span>

### <a name="basis--pauli"></a><span data-ttu-id="8ad6e-112">Podstawa: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="8ad6e-112">basis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="8ad6e-113">Operator Pauli $P $.</span><span class="sxs-lookup"><span data-stu-id="8ad6e-113">A Pauli operator $P$.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="8ad6e-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="8ad6e-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="8ad6e-115">Qubit do przygotowania.</span><span class="sxs-lookup"><span data-stu-id="8ad6e-115">A qubit to be prepared.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8ad6e-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8ad6e-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

