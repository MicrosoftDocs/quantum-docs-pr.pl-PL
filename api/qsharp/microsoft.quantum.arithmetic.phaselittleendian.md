---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 45b824a74d664df0d5707264a3c616fb27c477b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222426"
---
# <a name="phaselittleendian-user-defined-type"></a>PhaseLittleEndian typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. arytmetyczna](xref:Microsoft.Quantum.Arithmetic)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Małe liczby całkowite bez znaku endian w QFT.

Na przykład jeśli $ \ket{x} $ jest kodowaniem little-endian liczby całkowitej $x $ w oparciu o obliczenia, a następnie $ \operatorname{QFTLE} \ket{x} $ to kodowanie $x $ na podstawie QFT.

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>Uwagi

Skracamy `PhaseLittleEndian` `PhaseLE` się w dokumentacji.

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Microsoft. Quantum. Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)