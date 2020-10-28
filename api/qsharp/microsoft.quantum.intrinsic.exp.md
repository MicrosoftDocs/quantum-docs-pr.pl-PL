---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operacja EXP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: b923374a954f90aba2deaead79dd419fbf67fea3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711522"
---
# <a name="exp-operation"></a><span data-ttu-id="874e4-102">Operacja EXP</span><span class="sxs-lookup"><span data-stu-id="874e4-102">Exp operation</span></span>

<span data-ttu-id="874e4-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="874e4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="874e4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="874e4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="874e4-105">Stosuje wykładniczą qubit wieloskładnikowego operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="874e4-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="874e4-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align}, gdzie $P _i $ to $i $ th elementu `paulis` i gdzie $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="874e4-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="874e4-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="874e4-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="874e4-108">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="874e4-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="874e4-109">Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.</span><span class="sxs-lookup"><span data-stu-id="874e4-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="874e4-110">teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="874e4-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="874e4-111">Kąt dotyczący danego operatora qubit Pauli, za pomocą którego ma zostać obrócony rejestr docelowy.</span><span class="sxs-lookup"><span data-stu-id="874e4-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="874e4-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="874e4-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="874e4-113">Zarejestruj się, aby zastosować dany obrót do.</span><span class="sxs-lookup"><span data-stu-id="874e4-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="874e4-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="874e4-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

