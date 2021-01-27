---
uid: Microsoft.Quantum.Arithmetic.Carry
title: Przenieś operację
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: Carry
qsharp.summary: Implements a reversible carry gate. Given a carry-in bit encoded in qubit `carryIn` and two summand bits encoded in `summand1` and `summand2`, computes the bitwise xor of `carryIn`, `summand1` and `summand2` in the qubit `summand2` and the carry-out is xored to the qubit `carryOut`.
ms.openlocfilehash: dfb08a9a9c805c0b611ab993c9b1eb949810a7da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843354"
---
# <a name="carry-operation"></a>Przenieś operację

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementuje bramę przenoszące odwracalnie. Nadano bit przenoszenia zakodowany w qubit `carryIn` i dwie summand bity zakodowane w `summand1` i `summand2` , oblicza bitową XOR `carryIn` , `summand1` a `summand2` w qubit `summand2` i przeprowadzenie jest XORed do qubit `carryOut` .

```qsharp
operation Carry (carryIn : Qubit, summand1 : Qubit, summand2 : Qubit, carryOut : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="carryin--qubit"></a>przeprowadzenie: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit.


### <a name="summand1--qubit"></a>summand1: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Pierwszy summand qubit.


### <a name="summand2--qubit"></a>summand2: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Druga summand qubit jest zastępowana dolną bitową sumą `summand1` i `summand2` .


### <a name="carryout--qubit"></a>carryOut: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Przeprowadzenie qubit, będzie XORed z wyższą bitową sumą.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

