---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 5376b6f39d12d664342fbf71e67442c6ef8a0827
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202553"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="188aa-102">AllowAtMostNQubits, operacja</span><span class="sxs-lookup"><span data-stu-id="188aa-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="188aa-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="188aa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="188aa-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="188aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="188aa-105">Między wywołaniem tej operacji i jej częścią, potwierdzenia, że co najwyżej dana liczba dodatkowych qubits są przydzielane przy użyciu instrukcji using.</span><span class="sxs-lookup"><span data-stu-id="188aa-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="188aa-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="188aa-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="188aa-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="188aa-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="188aa-108">Maksymalna liczba qubits, które mogą być przydzieloną.</span><span class="sxs-lookup"><span data-stu-id="188aa-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="188aa-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="188aa-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="188aa-110">Komunikat, który ma być wyświetlany w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="188aa-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="188aa-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="188aa-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="188aa-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="188aa-112">Remarks</span></span>

<span data-ttu-id="188aa-113">Ta operacja może zostać zamieniona na elementy docelowe, które ich nie obsługują.</span><span class="sxs-lookup"><span data-stu-id="188aa-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>