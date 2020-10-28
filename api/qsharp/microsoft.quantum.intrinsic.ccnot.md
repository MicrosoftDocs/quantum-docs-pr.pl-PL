---
uid: Microsoft.Quantum.Intrinsic.CCNOT
title: CCNOT, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CCNOT
qsharp.summary: Applies the doubly controlled–NOT (CCNOT) gate to three qubits.
ms.openlocfilehash: bf20ff1e9d25d72e7e8e0207ab947a57dc394cf4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711536"
---
# <a name="ccnot-operation"></a><span data-ttu-id="645c8-102">CCNOT, operacja</span><span class="sxs-lookup"><span data-stu-id="645c8-102">CCNOT operation</span></span>

<span data-ttu-id="645c8-103">Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="645c8-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="645c8-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="645c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="645c8-105">Stosuje bramę z kontrolą podwójną — nie (CCNOT) do trzech qubits.</span><span class="sxs-lookup"><span data-stu-id="645c8-105">Applies the doubly controlled–NOT (CCNOT) gate to three qubits.</span></span>

```qsharp
operation CCNOT (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="645c8-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="645c8-106">Input</span></span>

### <a name="control1--qubit"></a><span data-ttu-id="645c8-107">Control1: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="645c8-107">control1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="645c8-108">Pierwszy Control qubit dla bramy CCNOT.</span><span class="sxs-lookup"><span data-stu-id="645c8-108">First control qubit for the CCNOT gate.</span></span>


### <a name="control2--qubit"></a><span data-ttu-id="645c8-109">Control2: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="645c8-109">control2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="645c8-110">Druga kontrolka qubit dla bramy CCNOT.</span><span class="sxs-lookup"><span data-stu-id="645c8-110">Second control qubit for the CCNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="645c8-111">obiekt docelowy: [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="645c8-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="645c8-112">Docelowa qubit dla bramy CCNOT.</span><span class="sxs-lookup"><span data-stu-id="645c8-112">Target qubit for the CCNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="645c8-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="645c8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="645c8-114">Uwagi</span><span class="sxs-lookup"><span data-stu-id="645c8-114">Remarks</span></span>

<span data-ttu-id="645c8-115">Równoważne:</span><span class="sxs-lookup"><span data-stu-id="645c8-115">Equivalent to:</span></span>

```qsharp
Controlled X([control1, control2], target);
```