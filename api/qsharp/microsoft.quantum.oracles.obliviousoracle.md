---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842562"
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