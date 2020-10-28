---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: ReflectionOracle typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724210"
---
# <a name="reflectionoracle-user-defined-type"></a>ReflectionOracle typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Package [](https://nuget.org/packages/)


Reprezentuje odbicie Oracle.

Odbicie Oracle, $O $, ma dane wejściowe:

- Faza $ \phi $, przez którą ma zostać obrócony odbicie.
- Rejestr qubit, w którym ma zostać wykonane odpowiednie odbicie.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Nazwane elementy

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL



## <a name="remarks"></a>Uwagi

Ta Oracle $O = \boldone-(1-e ^ {i \phi}) \ket{\psi}\bra{\psi} $ wykonuje częściowe odbicie według fazy $ \phi $ o pojedynczym czystym stanie $ \ket{\psi} $.