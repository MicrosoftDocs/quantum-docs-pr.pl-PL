---
uid: Microsoft.Quantum.Intrinsic.T
title: Operacja T
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720852"
---
# <a name="t-operation"></a><span data-ttu-id="36f4b-102">Operacja T</span><span class="sxs-lookup"><span data-stu-id="36f4b-102">T operation</span></span>

<span data-ttu-id="36f4b-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="36f4b-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="36f4b-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36f4b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36f4b-105">Stosuje bramę T do jednego qubit.</span><span class="sxs-lookup"><span data-stu-id="36f4b-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="36f4b-106">Opis</span><span class="sxs-lookup"><span data-stu-id="36f4b-106">Description</span></span>

<span data-ttu-id="36f4b-107">Ta operacja może być symulowana przez macierz jednostkową \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="36f4b-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="36f4b-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="36f4b-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="36f4b-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="36f4b-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="36f4b-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="36f4b-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="36f4b-111">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="36f4b-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36f4b-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36f4b-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

