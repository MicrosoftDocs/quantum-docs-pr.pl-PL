---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843202"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Reprezentuje rejestr qubits kodowania o stałej liczbie punktów. Składa się z liczby całkowitej, która jest równa liczbie qubits z lewej strony punktu binarnego, czyli qubits wagi większej lub równej 1 oraz rejestr Quantum.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

