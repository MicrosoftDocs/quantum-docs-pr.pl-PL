---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 6077110cc07c8626b22eb404c1de096ed43efcc3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224245"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Koduje wieloqubitowy operator Pauli reprezentowany jako tablica operatorów typu Single-qubit Pauli w postaci liczby całkowitej.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Dane wejściowe

### <a name="paulis--pauli"></a>Pawła: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Tablica z co najwyżej 31 operatorami jednoqubitowych Pauli.



## <a name="output--int"></a>Wynik: [int](xref:microsoft.quantum.lang-ref.int)

Unikatowa identyfikacja liczby całkowitej `paulis` , zgodnie z poniższym opisem.

## <a name="remarks"></a>Uwagi

Każdy operator Pauli można zakodować przy użyciu dwóch bitów: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $ $

Dana tablica operatorów Pauli `[P0, ..., Pn]` , ta funkcja zwraca liczbę całkowitą z rozszerzeniem binarnym, łącząc mapowania każdego operatora Pauli w kolejności big-endian `bits(Pn) ... bits(P0)` .