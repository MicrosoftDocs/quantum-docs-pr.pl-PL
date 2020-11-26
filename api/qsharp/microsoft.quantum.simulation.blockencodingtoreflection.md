---
uid: Microsoft.Quantum.Simulation.BlockEncodingToReflection
title: BlockEncodingToReflection, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingToReflection
qsharp.summary: >-
  Converts a `BlockEncoding` into an equivalent `BLockEncodingReflection`.

  That is, given a `BlockEncoding` unitary $U$ that encodes some operator $H$ of interest, converts it into a `BlockEncodingReflection` $U'$ that encodes the same operator, but also satisfies $U'^\dagger = U'$. This increases the size of the auxiliary register of $U$ by one qubit.
ms.openlocfilehash: 742d4f5623c7c26810998f6c96e2c7b05cc452d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225350"
---
# <a name="blockencodingtoreflection-function"></a>BlockEncodingToReflection, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Konwertuje element na `BlockEncoding` odpowiednik `BLockEncodingReflection` .

Oznacza to, że w przypadku `BlockEncoding` jednostkowego $U $, który koduje część operatora $H $ Interest, konwertuje ją na `BlockEncodingReflection` $U "$, który koduje ten sam operator, ale również spełnia $U" ^ \Dagger = U "$.
Zwiększa to rozmiar pomocniczego rejestru $U $ przez jeden qubit.

```qsharp
function BlockEncodingToReflection (blockEncoding : Microsoft.Quantum.Simulation.BlockEncoding) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Dane wejściowe

### <a name="blockencoding--blockencoding"></a>blockEncoding: [blockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)

`BlockEncoding`$U jednostkowe $ do przekonwertowania na odbicie.



## <a name="output--blockencodingreflection"></a>Wynik: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Jednostkowy $U "$ działa wspólnie w przypadku rejestrów `a` i `s` blokują $H $ i spełniają $U" ^ \Dagger = U "$.

## <a name="remarks"></a>Uwagi

Zwiększa to rozmiar pomocniczego rejestru $U $ przez jeden qubit.

## <a name="references"></a>Odwołania

- Symulacja hamiltonian przez Qubitization Guang przerywają Hao Low, Tomasz L. Czuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Symulacja. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Symulacja. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)