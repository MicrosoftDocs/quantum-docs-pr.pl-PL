---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721149"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Reprezentuje rejestr qubits kodowania o stałej liczbie punktów. Składa się z liczby całkowitej, która jest równa liczbie qubits z lewej strony punktu binarnego, czyli qubits wagi większej lub równej 1 oraz rejestr Quantum.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

