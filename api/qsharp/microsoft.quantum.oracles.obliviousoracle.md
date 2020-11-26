---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 2f92dcb28ec669229dfaf9bcb23eef9234552b8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193883"
---
# <a name="obliviousoracle-user-defined-type"></a>ObliviousOracle typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje wzmocnienie amplitudy Oracle for Oblivious.

Dane wejściowe programu Oracle $O $ to:

- $A rejestru Ancilla $ $O $.
- System rejestruje $s $, na którym jest zastosowana żądana jednostka $U $, po wybraniu rejestracji $a $ w stanie $ \ket{t} \_ a $.

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>Uwagi

Ta Oracle zdefiniowana przez $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ działa w stanie Ancilla $ \ket{s} \_ a $, aby zaimplementować jednostkę $U $ na dowolnym stanie systemu $ \ket{\psi} \_ s $ z amplitudą $ \lambda $ na podstawie oflagowanej przez $ \ket{t} \_ a $.
Pierwszy parametr jest rejestrem qubit $ \ket{s} \_ a $. Drugi parametr jest rejestrem qubit $ \ket{\psi} \_ s $.