---
uid: Microsoft.Quantum.Arithmetic.Sum
title: Suma operacji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Sum
qsharp.summary: Implements a reversible sum gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2`.
ms.openlocfilehash: b31d8ab39676ee6723e5fc053eba9e0af3ac2b2f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719505"
---
# <a name="sum-operation"></a>Suma operacji

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Package [](https://nuget.org/packages/)


Implementuje bramę sum odwracalnych. Nadawana jest zakodowana w qubit `carryIn` i dwie summand bity zakodowane w `summand1` i `summand2` , które oblicza bitowe XOR `carryIn` `summand1` i `summand2` w qubit `summand2` .

```qsharp
operation Sum (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="carryin--qubit"></a>przeprowadzenie: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit.


### <a name="summand1--qubit"></a>summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pierwszy summand qubit.


### <a name="summand2--qubit"></a>summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druga summand qubit jest zastępowana dolną bitową sumą `summand1` i `summand2` .



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

W przeciwieństwie do `Carry` operacji to nie oblicza bitu przeprowadzenia.