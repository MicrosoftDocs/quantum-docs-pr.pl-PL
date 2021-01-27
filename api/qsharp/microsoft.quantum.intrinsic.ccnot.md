---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: a9186269a868c2ac9d2f15727a3b0ed1bfec3fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819027"
---
# <a name="ccnot-operation"></a><span data-ttu-id="3b713-102">CCNOT, operacja</span><span class="sxs-lookup"><span data-stu-id="3b713-102">CCNOT operation</span></span>

<span data-ttu-id="3b713-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="3b713-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="3b713-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3b713-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3b713-105">Stosuje bramę z kontrolą podwójną — nie (CCNOT) do trzech qubits.</span><span class="sxs-lookup"><span data-stu-id="3b713-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="3b713-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3b713-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="3b713-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3b713-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3b713-108">Pierwszy Control qubit dla bramy CCNOT.</span><span class="sxs-lookup"><span data-stu-id="3b713-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="3b713-109">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3b713-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3b713-110">Druga kontrolka qubit dla bramy CCNOT.</span><span class="sxs-lookup"><span data-stu-id="3b713-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="3b713-111">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="3b713-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="3b713-112">Docelowa qubit dla bramy CCNOT.</span><span class="sxs-lookup"><span data-stu-id="3b713-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b713-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b713-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="3b713-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3b713-114">Remarks</span></span>

<span data-ttu-id="3b713-115">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="3b713-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```