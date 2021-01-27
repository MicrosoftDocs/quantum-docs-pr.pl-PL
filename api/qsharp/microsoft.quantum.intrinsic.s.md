---
uid: Microsoft.Quantum.Intrinsic.S
title: Operacja S
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: S
qsharp.summary: Applies the S gate to a single qubit.
ms.openlocfilehash: be9078dfdcc4eecf317b0542b1c42a8d60466a5f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817535"
---
# <a name="s-operation"></a><span data-ttu-id="474ea-102">Operacja S</span><span class="sxs-lookup"><span data-stu-id="474ea-102">S operation</span></span>

<span data-ttu-id="474ea-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="474ea-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="474ea-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="474ea-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="474ea-105">Stosuje bramę S do jednego qubitu.</span><span class="sxs-lookup"><span data-stu-id="474ea-105">Applies the S gate to a single qubit.</span></span>

```qsharp
operation S (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="474ea-106">Opis</span><span class="sxs-lookup"><span data-stu-id="474ea-106">Description</span></span>

<span data-ttu-id="474ea-107">Ta operacja może być symulowana przez macierz jednostkową \begin{align} S \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & i \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="474ea-107">This operation can be simulated by the unitary matrix \begin{align} S \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="474ea-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="474ea-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="474ea-109">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="474ea-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="474ea-110">qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="474ea-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="474ea-111">Qubit, do którego należy zastosować bramę.</span><span class="sxs-lookup"><span data-stu-id="474ea-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="474ea-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="474ea-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

