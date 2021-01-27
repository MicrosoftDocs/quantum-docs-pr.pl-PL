---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Operacja EXP
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819009"
---
# <a name="exp-operation"></a><span data-ttu-id="04dd8-102">Operacja EXP</span><span class="sxs-lookup"><span data-stu-id="04dd8-102">Exp operation</span></span>

<span data-ttu-id="04dd8-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="04dd8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="04dd8-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="04dd8-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="04dd8-105">Stosuje wykładniczą qubit wieloskładnikowego operatora Pauli.</span><span class="sxs-lookup"><span data-stu-id="04dd8-105">Applies the exponential of a multi-qubit Pauli operator.</span></span>

<span data-ttu-id="04dd8-106">\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}, \end{align}, gdzie $P _i $ to $i $ th elementu `paulis` i gdzie $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="04dd8-106">\begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="04dd8-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="04dd8-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="04dd8-108">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="04dd8-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="04dd8-109">Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.</span><span class="sxs-lookup"><span data-stu-id="04dd8-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="theta--double"></a><span data-ttu-id="04dd8-110">teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="04dd8-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="04dd8-111">Kąt dotyczący danego operatora qubit Pauli, za pomocą którego ma zostać obrócony rejestr docelowy.</span><span class="sxs-lookup"><span data-stu-id="04dd8-111">Angle about the given multi-qubit Pauli operator by which the target register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="04dd8-112">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="04dd8-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="04dd8-113">Zarejestruj się, aby zastosować dany obrót do.</span><span class="sxs-lookup"><span data-stu-id="04dd8-113">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="04dd8-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04dd8-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

