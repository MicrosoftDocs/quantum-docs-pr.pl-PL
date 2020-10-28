---
uid: Microsoft.Quantum.Intrinsic.T
title: Operacja T
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720852"
---
# <a name="t-operation"></a>Operacja T

Przestrzeń nazw: [Microsoft. Quantum. wewnętrzna](xref:Microsoft.Quantum.Intrinsic)

Package [](https://nuget.org/packages/)


Stosuje bramę T do jednego qubit.

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a>Opis

Ta operacja może być symulowana przez macierz jednostkową \begin{align} T \mathrel{: =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}.
\end{align}

## <a name="input"></a>Dane wejściowe

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, do którego należy zastosować bramę.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

