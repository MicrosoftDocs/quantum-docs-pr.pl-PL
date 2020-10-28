---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723510"
---
# <a name="rfrac-operation"></a><span data-ttu-id="bf7ff-102">RFrac, operacja</span><span class="sxs-lookup"><span data-stu-id="bf7ff-102">RFrac operation</span></span>

<span data-ttu-id="bf7ff-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="bf7ff-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="bf7ff-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf7ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf7ff-105">Stosuje obrót dotyczący danej osi Pauli o kąt określony jako ułamek dyadic.</span><span class="sxs-lookup"><span data-stu-id="bf7ff-105">Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="bf7ff-106">\begin{align} R_ {\mu} (n, k) \mathrel{: =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}, \end{align} gdzie $ \mu \In \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="bf7ff-106">\begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

> [!WARNING]
> <span data-ttu-id="bf7ff-107">Ta operacja używa **przeciwległej** Konwencji podpisywania z @"microsoft.quantum.intrinsic.r" .</span><span class="sxs-lookup"><span data-stu-id="bf7ff-107">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r".</span></span>

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bf7ff-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bf7ff-108">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="bf7ff-109">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="bf7ff-109">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="bf7ff-110">Operator Pauli, który ma być exponentiated do tworzenia obrotu.</span><span class="sxs-lookup"><span data-stu-id="bf7ff-110">Pauli operator to be exponentiated to form the rotation.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="bf7ff-111">Licznik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf7ff-111">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf7ff-112">Licznik w reprezentacji dyadic ułamek kąta, do którego ma zostać obrócony qubit.</span><span class="sxs-lookup"><span data-stu-id="bf7ff-112">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="bf7ff-113">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bf7ff-113">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bf7ff-114">Potęga dwóch określająca mianownik kąta, do którego ma zostać obrócony qubit.</span><span class="sxs-lookup"><span data-stu-id="bf7ff-114">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="bf7ff-115">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bf7ff-115">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bf7ff-116">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="bf7ff-116">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf7ff-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf7ff-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bf7ff-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="bf7ff-118">Remarks</span></span>

<span data-ttu-id="bf7ff-119">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="bf7ff-119">Equivalent to:</span></span>

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```