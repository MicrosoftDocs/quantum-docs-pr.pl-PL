---
uid: Microsoft.Quantum.Canon.CY
title: CY — operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 862f058e630ee6d9159e0fe514ca2dd1179ea9a2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840737"
---
# <a name="cy-operation"></a><span data-ttu-id="eb91c-102">CY — operacja</span><span class="sxs-lookup"><span data-stu-id="eb91c-102">CY operation</span></span>

<span data-ttu-id="eb91c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb91c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb91c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb91c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb91c-105">Stosuje bramę kontrolowane-Y (CY) do pary qubits.</span><span class="sxs-lookup"><span data-stu-id="eb91c-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="eb91c-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & i & 0 \end{align}, $ $, gdzie wiersze i kolumny są zorganizowane jak w przewodniku koncepcji Quantum.</span><span class="sxs-lookup"><span data-stu-id="eb91c-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="eb91c-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="eb91c-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="eb91c-108">Kontrolka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb91c-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb91c-109">Kontrolka qubit dla bramy CY.</span><span class="sxs-lookup"><span data-stu-id="eb91c-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="eb91c-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eb91c-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eb91c-111">Docelowa qubit dla bramy CY.</span><span class="sxs-lookup"><span data-stu-id="eb91c-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb91c-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb91c-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="eb91c-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="eb91c-113">Remarks</span></span>

<span data-ttu-id="eb91c-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="eb91c-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```