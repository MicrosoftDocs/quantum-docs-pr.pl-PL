---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223106"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="84084-102">FixedPoint typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="84084-102">FixedPoint user defined type</span></span>

<span data-ttu-id="84084-103">Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="84084-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="84084-104">Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="84084-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="84084-105">Reprezentuje rejestr qubits kodowania o stałej liczbie punktów.</span><span class="sxs-lookup"><span data-stu-id="84084-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="84084-106">Składa się z liczby całkowitej, która jest równa liczbie qubits z lewej strony punktu binarnego, czyli qubits wagi większej lub równej 1 oraz rejestr Quantum.</span><span class="sxs-lookup"><span data-stu-id="84084-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

