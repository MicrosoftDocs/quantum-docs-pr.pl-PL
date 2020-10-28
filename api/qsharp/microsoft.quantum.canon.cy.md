---
uid: Microsoft.Quantum.Canon.CY
title: CY — operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716361"
---
# <a name="cy-operation"></a><span data-ttu-id="b02d0-102">CY — operacja</span><span class="sxs-lookup"><span data-stu-id="b02d0-102">CY operation</span></span>

<span data-ttu-id="b02d0-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b02d0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b02d0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b02d0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b02d0-105">Stosuje bramę kontrolowane-Y (CY) do pary qubits.</span><span class="sxs-lookup"><span data-stu-id="b02d0-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="b02d0-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}, $ $, gdzie wiersze i kolumny są zorganizowane jak w przewodniku koncepcji Quantum.</span><span class="sxs-lookup"><span data-stu-id="b02d0-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="b02d0-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b02d0-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="b02d0-108">Kontrolka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b02d0-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b02d0-109">Kontrolka qubit dla bramy CY.</span><span class="sxs-lookup"><span data-stu-id="b02d0-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="b02d0-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="b02d0-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="b02d0-111">Docelowa qubit dla bramy CY.</span><span class="sxs-lookup"><span data-stu-id="b02d0-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b02d0-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b02d0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="b02d0-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b02d0-113">Remarks</span></span>

<span data-ttu-id="b02d0-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="b02d0-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```