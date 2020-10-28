---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713057"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="d8552-102">AllowAtMostNQubits, operacja</span><span class="sxs-lookup"><span data-stu-id="d8552-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="d8552-103">Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="d8552-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="d8552-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d8552-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d8552-105">Między wywołaniem tej operacji i jej częścią, potwierdzenia, że co najwyżej dana liczba dodatkowych qubits są przydzielane przy użyciu instrukcji using.</span><span class="sxs-lookup"><span data-stu-id="d8552-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="d8552-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d8552-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="d8552-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d8552-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d8552-108">Maksymalna liczba qubits, które mogą być przydzieloną.</span><span class="sxs-lookup"><span data-stu-id="d8552-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="d8552-109">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="d8552-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="d8552-110">Komunikat, który ma być wyświetlany w przypadku awarii.</span><span class="sxs-lookup"><span data-stu-id="d8552-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d8552-111">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8552-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d8552-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="d8552-112">Remarks</span></span>

<span data-ttu-id="d8552-113">Ta operacja może zostać zamieniona na elementy docelowe, które ich nie obsługują.</span><span class="sxs-lookup"><span data-stu-id="d8552-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>