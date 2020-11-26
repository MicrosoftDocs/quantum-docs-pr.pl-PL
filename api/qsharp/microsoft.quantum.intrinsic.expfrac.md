---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 8ccea068dd61aaf8c1ba384969adef5644e8401e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198999"
---
# <a name="expfrac-operation"></a><span data-ttu-id="cf1b9-102">ExpFrac, operacja</span><span class="sxs-lookup"><span data-stu-id="cf1b9-102">ExpFrac operation</span></span>

<span data-ttu-id="cf1b9-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cf1b9-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cf1b9-105">Stosuje wykładniczą qubit wieloskładnikowego operatora Pauli z argumentem podanym przez ułamek dyadic.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="cf1b9-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align}, gdzie $P _i $ to $i $ th elementu `paulis` , i gdzie $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="cf1b9-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cf1b9-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="cf1b9-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="cf1b9-108">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="cf1b9-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="cf1b9-109">Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="cf1b9-110">Licznik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cf1b9-111">Licznik ($k $) w reprezentacji dyadic frakcji kąta, za pomocą którego ma zostać obrócony rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="cf1b9-112">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cf1b9-113">Potęgi dwóch ($n $) określające mianownik kąta, w którym ma zostać obrócony rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cf1b9-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cf1b9-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cf1b9-115">Zarejestruj się, aby zastosować dany obrót do.</span><span class="sxs-lookup"><span data-stu-id="cf1b9-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cf1b9-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cf1b9-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

