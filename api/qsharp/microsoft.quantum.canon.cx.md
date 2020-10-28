---
uid: Microsoft.Quantum.Canon.CX
title: Operacja CX
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716375"
---
# <a name="cx-operation"></a><span data-ttu-id="53788-102">Operacja CX</span><span class="sxs-lookup"><span data-stu-id="53788-102">CX operation</span></span>

<span data-ttu-id="53788-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="53788-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="53788-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="53788-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="53788-105">Stosuje bramę z kontrolą X (CX) do pary qubits.</span><span class="sxs-lookup"><span data-stu-id="53788-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="53788-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, gdzie wiersze i kolumny są zorganizowane jak w przewodniku koncepcji Quantum.</span><span class="sxs-lookup"><span data-stu-id="53788-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="53788-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="53788-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="53788-108">Kontrolka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="53788-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="53788-109">Kontrolka qubit dla bramy CX.</span><span class="sxs-lookup"><span data-stu-id="53788-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="53788-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="53788-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="53788-111">Docelowa qubit dla bramy CX.</span><span class="sxs-lookup"><span data-stu-id="53788-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="53788-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="53788-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="53788-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="53788-113">Remarks</span></span>

<span data-ttu-id="53788-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="53788-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="53788-115">i do:</span><span class="sxs-lookup"><span data-stu-id="53788-115">and to:</span></span>

```qsharp
CNOT(control, target);
```