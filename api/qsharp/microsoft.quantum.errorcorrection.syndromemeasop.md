---
uid: Microsoft.Quantum.ErrorCorrection.SyndromeMeasOp
title: SyndromeMeasOp typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SyndromeMeasOp
qsharp.summary: Represents an operation that is used to measure the syndrome of an error-correcting code block.
ms.openlocfilehash: 65e47d82546b1df0beec2c00f435d3e7a28e6ae6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200258"
---
# <a name="syndromemeasop-user-defined-type"></a><span data-ttu-id="24e87-102">SyndromeMeasOp typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="24e87-102">SyndromeMeasOp user defined type</span></span>

<span data-ttu-id="24e87-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="24e87-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="24e87-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24e87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24e87-105">Reprezentuje operację, która jest używana do mierzenia Syndrome w bloku kodu z korekcją błędów.</span><span class="sxs-lookup"><span data-stu-id="24e87-105">Represents an operation that is used to measure the syndrome of an error-correcting code block.</span></span>

```qsharp

newtype SyndromeMeasOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => Microsoft.Quantum.ErrorCorrection.Syndrome));
```



## <a name="remarks"></a><span data-ttu-id="24e87-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="24e87-106">Remarks</span></span>

<span data-ttu-id="24e87-107">Sygnatura `(LogicalRegister => Syndrome)` reprezentuje operację, która działa wspólnie na qubits w `LogicalRegister` i niektórych qubits pomocniczych, a następnie obejmuje pomiary qubits pomocniczych w celu wyodrębnienia `Syndrome` wartości reprezentującej `Result[]` te pomiary.</span><span class="sxs-lookup"><span data-stu-id="24e87-107">The signature `(LogicalRegister => Syndrome)` represents an operation that acts jointly on the qubits in `LogicalRegister` and some auxiliary qubits followed by a measurements of the auxiliary qubits to extract a `Syndrome` value representing the `Result[]` of these measurements.</span></span>

## <a name="see-also"></a><span data-ttu-id="24e87-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="24e87-108">See Also</span></span>

- [<span data-ttu-id="24e87-109">Microsoft. Quantum. ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="24e87-109">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [<span data-ttu-id="24e87-110">Microsoft. Quantum. ErrorCorrection. Syndrome</span><span class="sxs-lookup"><span data-stu-id="24e87-110">Microsoft.Quantum.ErrorCorrection.Syndrome</span></span>](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)