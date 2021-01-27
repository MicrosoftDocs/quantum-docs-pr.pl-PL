---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: c6c9b5724354d6ee034dd8b6733901ebdd8072d6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856868"
---
# <a name="preparesinglequbitidentity-operation"></a>PrepareSingleQubitIdentity, operacja

Przestrzeń nazw: [Microsoft. Quantum. przygotowaniu](xref:Microsoft.Quantum.Preparation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Przygotowuje qubit w stanie mieszanym Maximally.

Przygotowuje daną qubit w stanie $ \boldone/$2 przez zastosowanie depolarizing kanału $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ sum_ {\mu \In \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ WHERE $ \sigma \_ i $ jest operatorem $i $ th Pauli i gdzie $ \rho $ jest operatorem gęstości reprezentującym stan mieszany.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="qubit--qubit"></a>qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit, którego stan ma zostać określony w sposób opisany powyżej.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Stan mieszany $ \boldone/$2 opisujący wynik zastosowania tej operacji do stanu niejawnie opisuje wartość oczekiwaną w przypadku losowych wyborów wykonanych w tej operacji.
W tym przypadku dla każdej pojedynczej aplikacji ta operacja mapuje czyste Stany w czyste Stany, ale działa zgodnie z opisem w temacie oczekiwanie.
W szczególności tej operacji można użyć w procesie Tomography, aby mierzyć składniki *niebędące jednostką* kanału.