---
uid: Microsoft.Quantum.Intrinsic.T
title: Operacja T
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817511"
---
# <a name="t-operation"></a><span data-ttu-id="40da4-102">Operacja T</span><span class="sxs-lookup"><span data-stu-id="40da4-102">T operation</span></span>

<span data-ttu-id="40da4-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="40da4-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="40da4-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="40da4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="40da4-105">Stosuje bramę T do jednego qubit.</span><span class="sxs-lookup"><span data-stu-id="40da4-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="40da4-106">Opis</span><span class="sxs-lookup"><span data-stu-id="40da4-106">Description</span></span>

<span data-ttu-id="40da4-107">Ta operacja może być symulowana przez macierz jednostkową \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="40da4-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="40da4-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="40da4-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="40da4-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="40da4-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="40da4-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="40da4-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="40da4-111">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="40da4-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="40da4-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="40da4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

