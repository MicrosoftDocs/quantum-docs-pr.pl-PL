---
uid: Microsoft.Quantum.Canon.CX
title: Operacja CX
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4eaecf372f3054de4886b1e42c6b4ce386a22f73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207245"
---
# <a name="cx-operation"></a><span data-ttu-id="9b442-102">Operacja CX</span><span class="sxs-lookup"><span data-stu-id="9b442-102">CX operation</span></span>

<span data-ttu-id="9b442-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b442-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b442-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b442-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b442-105">Stosuje bramę z kontrolą X (CX) do pary qubits.</span><span class="sxs-lookup"><span data-stu-id="9b442-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="9b442-106">$ $ \begin{align} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{Matrix}\right) \end{align}, $ $, gdzie wiersze i kolumny są zorganizowane jak w przewodniku koncepcji Quantum.</span><span class="sxs-lookup"><span data-stu-id="9b442-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9b442-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9b442-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="9b442-108">Kontrolka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b442-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b442-109">Kontrolka qubit dla bramy CX.</span><span class="sxs-lookup"><span data-stu-id="9b442-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9b442-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9b442-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9b442-111">Docelowa qubit dla bramy CX.</span><span class="sxs-lookup"><span data-stu-id="9b442-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b442-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b442-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9b442-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9b442-113">Remarks</span></span>

<span data-ttu-id="9b442-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="9b442-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="9b442-115">i do:</span><span class="sxs-lookup"><span data-stu-id="9b442-115">and to:</span></span>

```qsharp
CNOT(control, target);
```