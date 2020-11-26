---
uid: Microsoft.Quantum.Intrinsic.T
title: Operacja T
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 352ef2c1b15a46dea85c420fc6f1cfab0382e73a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198405"
---
# <a name="t-operation"></a><span data-ttu-id="4fb42-102">Operacja T</span><span class="sxs-lookup"><span data-stu-id="4fb42-102">T operation</span></span>

<span data-ttu-id="4fb42-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4fb42-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4fb42-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4fb42-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4fb42-105">Stosuje bramę T do jednego qubit.</span><span class="sxs-lookup"><span data-stu-id="4fb42-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="4fb42-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4fb42-106">Description</span></span>

<span data-ttu-id="4fb42-107">Ta operacja może być symulowana przez macierz jednostkową \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4fb42-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="4fb42-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="4fb42-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="4fb42-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4fb42-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="4fb42-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4fb42-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4fb42-111">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="4fb42-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4fb42-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4fb42-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

