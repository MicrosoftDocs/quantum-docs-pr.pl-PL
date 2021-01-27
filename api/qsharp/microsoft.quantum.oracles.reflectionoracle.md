---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854489"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje odbicie Oracle.

Odbicie Oracle, $O $, ma dane wejściowe:

- Faza $ \phi $, przez którą ma zostać obrócony odbicie.
- Rejestr qubit, w którym ma zostać wykonane odpowiednie odbicie.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Nazwane elementy

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL



## <a name="remarks"></a>Uwagi

Ta Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ wykonuje częściowe odbicie według fazy $ \phi $ o pojedynczym czystym stanie $ \ket{\psi} $.