---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711489"
---
# <a name="expfrac-operation"></a><span data-ttu-id="878e2-102">ExpFrac, operacja</span><span class="sxs-lookup"><span data-stu-id="878e2-102">ExpFrac operation</span></span>

<span data-ttu-id="878e2-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="878e2-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="878e2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="878e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="878e2-105">Stosuje wykładniczą qubit wieloskładnikowego operatora Pauli z argumentem podanym przez ułamek dyadic.</span><span class="sxs-lookup"><span data-stu-id="878e2-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="878e2-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align}, gdzie $P _i $ to $i $ th elementu `paulis` , i gdzie $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="878e2-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="878e2-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="878e2-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="878e2-108">Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="878e2-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="878e2-109">Tablica wartości qubit Pauli, wskazujących czynniki iloczynu dwubajtowego na każdym qubit.</span><span class="sxs-lookup"><span data-stu-id="878e2-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="878e2-110">Licznik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="878e2-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="878e2-111">Licznik ($k $) w reprezentacji dyadic frakcji kąta, za pomocą którego ma zostać obrócony rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="878e2-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="878e2-112">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="878e2-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="878e2-113">Potęgi dwóch ($n $) określające mianownik kąta, w którym ma zostać obrócony rejestr qubit.</span><span class="sxs-lookup"><span data-stu-id="878e2-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="878e2-114">qubits: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="878e2-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="878e2-115">Zarejestruj się, aby zastosować dany obrót do.</span><span class="sxs-lookup"><span data-stu-id="878e2-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="878e2-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="878e2-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

