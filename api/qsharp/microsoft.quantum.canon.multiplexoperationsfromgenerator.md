---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 59afa9d9a34fe74206118680940d243ed8b2496e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852492"
---
# <a name="multiplexoperationsfromgenerator-operation"></a>MultiplexOperationsFromGenerator, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Stosuje przemnożoną przez siebie operację jednostkową $U $, która stosuje $V jednostkowe _j $, gdy jest to kontrolowane przez n-qubit Number State $ \ket{j} $.

$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a>unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 'r => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL)

Krotka, w której pierwszy element `Int` jest liczbą unitaries $N $, a drugi element `(Int -> ('T => () is Adj + Ctl))` to funkcja, która przyjmuje liczbę całkowitą $j $ w $ [0, N-1] $ i wyprowadza operację jednostkową $V _j $.


### <a name="index--littleendian"></a>indeks: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $-qubit kontroli rejestru, który koduje liczbę Stany $ \ket{j} $ w formacie little-endian.


### <a name="target--t"></a>element docelowy: 'T

Ogólny rejestr qubit, który $V _j $ działa.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C



## <a name="remarks"></a>Uwagi

`coefficients` zostaną uzupełnione elementami tożsamości, jeśli określono mniej niż $2 ^ n $. Ta implementacja używa qubits pomocniczego $n-$1.

## <a name="references"></a>Odwołania

- [*Andrew M. Childs, Dmitri Maslov, Yunseong, Neila J. Ross, Juan Su*, ArXiv: 1711.10980](https://arxiv.org/abs/1711.10980)