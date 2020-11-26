---
uid: Microsoft.Quantum.Intrinsic.R
title: Operacja języka R
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 89aa5b2867068d4352a0b9550e8d22aa77439111
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96199033"
---
# <a name="r-operation"></a><span data-ttu-id="78012-102">Operacja języka R</span><span class="sxs-lookup"><span data-stu-id="78012-102">R operation</span></span>

<span data-ttu-id="78012-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="78012-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="78012-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="78012-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="78012-105">Stosuje obrót o podaną oś Pauli.</span><span class="sxs-lookup"><span data-stu-id="78012-105">Applies a rotation about the given Pauli axis.</span></span>

<span data-ttu-id="78012-106">\begin{align} R_ {\mu} (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_ {\mu}/2}, \end{align} gdzie $ \mu \In \{ i, X, Y, Z \} $.</span><span class="sxs-lookup"><span data-stu-id="78012-106">\begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.</span></span>

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="78012-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="78012-107">Input</span></span>

### <a name="pauli--pauli"></a><span data-ttu-id="78012-108">Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="78012-108">pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="78012-109">Operator Pauli ($ \mu $) ma być exponentiated do tworzenia obrotu.</span><span class="sxs-lookup"><span data-stu-id="78012-109">Pauli operator ($\mu$) to be exponentiated to form the rotation.</span></span>


### <a name="theta--double"></a><span data-ttu-id="78012-110">teta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="78012-110">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="78012-111">Kąt, dla którego ma zostać obrócony qubit.</span><span class="sxs-lookup"><span data-stu-id="78012-111">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="78012-112">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="78012-112">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="78012-113">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="78012-113">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="78012-114">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="78012-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="78012-115">Uwagi</span><span class="sxs-lookup"><span data-stu-id="78012-115">Remarks</span></span>

<span data-ttu-id="78012-116">Gdy jest wywoływana z `pauli = PauliI` , ta operacja stosuje *fazę globalną*.</span><span class="sxs-lookup"><span data-stu-id="78012-116">When called with `pauli = PauliI`, this operation applies a *global phase*.</span></span> <span data-ttu-id="78012-117">Ta faza może być istotna, gdy jest używana z `Controlled` Funktor.</span><span class="sxs-lookup"><span data-stu-id="78012-117">This phase can be significant when used with the `Controlled` functor.</span></span>