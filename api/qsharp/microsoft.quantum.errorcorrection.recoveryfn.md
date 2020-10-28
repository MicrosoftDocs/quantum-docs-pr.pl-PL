---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: RecoveryFn typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: 6f4db7312fadbd8ca4c6b8533f78c2c5a886f30e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712194"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="18cdf-102">RecoveryFn typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="18cdf-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="18cdf-103">Przestrzeń nazw: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="18cdf-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="18cdf-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="18cdf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="18cdf-105">Typ funkcji, która mapuje błąd Syndrome na sekwencję `Pauli[]` operacji, które korygują wykryty błąd.</span><span class="sxs-lookup"><span data-stu-id="18cdf-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

