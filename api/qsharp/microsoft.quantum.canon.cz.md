---
uid: Microsoft.Quantum.Canon.CZ
title: Operacja CZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716347"
---
# <a name="cz-operation"></a><span data-ttu-id="ac4c4-102">Operacja CZ</span><span class="sxs-lookup"><span data-stu-id="ac4c4-102">CZ operation</span></span>

<span data-ttu-id="ac4c4-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ac4c4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ac4c4-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac4c4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac4c4-105">Stosuje bramę z kontrolą Z (CZ) do pary qubits.</span><span class="sxs-lookup"><span data-stu-id="ac4c4-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="ac4c4-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}, $ $, gdzie wiersze i kolumny są zorganizowane jak w przewodniku koncepcji Quantum.</span><span class="sxs-lookup"><span data-stu-id="ac4c4-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ac4c4-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ac4c4-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="ac4c4-108">Kontrolka: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac4c4-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac4c4-109">Kontrolka qubit dla bramy "CZ".</span><span class="sxs-lookup"><span data-stu-id="ac4c4-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ac4c4-110">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ac4c4-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ac4c4-111">Docelowa qubit dla bramy "CZ".</span><span class="sxs-lookup"><span data-stu-id="ac4c4-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ac4c4-112">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ac4c4-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ac4c4-113">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ac4c4-113">Remarks</span></span>

<span data-ttu-id="ac4c4-114">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="ac4c4-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```