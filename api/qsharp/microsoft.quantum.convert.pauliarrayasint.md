---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713370"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Package [](https://nuget.org/packages/)


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