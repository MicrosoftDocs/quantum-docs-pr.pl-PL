---
uid: Microsoft.Quantum.Simulation.Unitary
title: Typ zdefiniowany przez użytkownika dla jednostki
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: c34d84fb5f319c285356b284bd1f1c18ec64ef46
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192149"
---
# <a name="unitary-user-defined-type"></a><span data-ttu-id="69207-102">Typ zdefiniowany przez użytkownika dla jednostki</span><span class="sxs-lookup"><span data-stu-id="69207-102">Unitary user defined type</span></span>

<span data-ttu-id="69207-103">Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="69207-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="69207-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69207-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69207-105">Reprezentuje ewolucję w ramach operatora jednostkowego.</span><span class="sxs-lookup"><span data-stu-id="69207-105">Represents evolution under a unitary operator.</span></span>

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

