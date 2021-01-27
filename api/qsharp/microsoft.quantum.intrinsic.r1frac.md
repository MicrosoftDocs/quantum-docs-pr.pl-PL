---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfae01d11524f64ceebd53aa8544d7ea48c40f31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818687"
---
# <a name="r1frac-operation"></a><span data-ttu-id="72341-102">R1Frac, operacja</span><span class="sxs-lookup"><span data-stu-id="72341-102">R1Frac operation</span></span>

<span data-ttu-id="72341-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="72341-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="72341-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="72341-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="72341-105">Stosuje obrót o stanie $ \ket {1} $ przez kąt określony jako ułamek dyadic.</span><span class="sxs-lookup"><span data-stu-id="72341-105">Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.</span></span>

<span data-ttu-id="72341-106">\begin{align} R_1 (n, k) \mathrel{: =} \operatorname{diag} (1, e ^ {i \pi k/2 ^ n}).</span><span class="sxs-lookup"><span data-stu-id="72341-106">\begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}).</span></span>
<span data-ttu-id="72341-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="72341-107">\end{align}</span></span>

> [!WARNING]
> <span data-ttu-id="72341-108">Ta operacja używa **przeciwległej** Konwencji podpisywania z @"microsoft.quantum.intrinsic.r" i nie obejmuje współczynnika $1/2 $ dołączonego przez @"microsoft.quantum.intrinsic.r1" .</span><span class="sxs-lookup"><span data-stu-id="72341-108">This operation uses the **opposite** sign convention from @"microsoft.quantum.intrinsic.r", and does not include the factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".</span></span>

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="72341-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="72341-109">Input</span></span>

### <a name="numerator--int"></a><span data-ttu-id="72341-110">Licznik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72341-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72341-111">Licznik w reprezentacji dyadic ułamek kąta, do którego ma zostać obrócony qubit.</span><span class="sxs-lookup"><span data-stu-id="72341-111">Numerator in the dyadic fraction representation of the angle by which the qubit is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="72341-112">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="72341-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="72341-113">Potęga dwóch określająca mianownik kąta, do którego ma zostać obrócony qubit.</span><span class="sxs-lookup"><span data-stu-id="72341-113">Power of two specifying the denominator of the angle by which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="72341-114">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="72341-114">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="72341-115">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="72341-115">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="72341-116">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72341-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="72341-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="72341-117">Remarks</span></span>

<span data-ttu-id="72341-118">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="72341-118">Equivalent to:</span></span>

```qsharp
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```