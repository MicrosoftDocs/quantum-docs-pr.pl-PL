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
# <a name="fixedpoint-user-defined-type"></a>FixedPoint typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Reprezentuje rejestr qubits kodowania o stałej liczbie punktów. Składa się z liczby całkowitej, która jest równa liczbie qubits z lewej strony punktu binarnego, czyli qubits wagi większej lub równej 1 oraz rejestr Quantum.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

