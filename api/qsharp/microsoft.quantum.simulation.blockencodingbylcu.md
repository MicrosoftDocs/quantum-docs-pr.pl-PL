---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229549"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Koduje operatora zainteresowania `BlockEncoding` .

To konstruuje `BlockEncoding` $U jednostkowe = P\cdot V\cdot P ^ \dagger $, który koduje niektóre operatory $H = \ sum_ {j} | \ alpha_j | U_j $ znaczenie, które jest liniową kombinacją unitaries. Zwykle $P $ jest jednostką przygotowań stanu, taką jak $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $, i $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Dane wejściowe

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL

Jednostkowy $P $, który przygotowuje jakiś stan docelowy.


### <a name="selector--ts--unit--is-adj--ctl"></a>Selektor: ('T,) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL

Jednostkowy $V $, który koduje składnik unitaries $H $.



## <a name="output--ts--unit--is-adj--ctl"></a>Wynik: (t,) = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL

Jednostkowe $U $ działające wspólnie z rejestrami `a` i tymi `s` , które zablokują $H $, i spełniają $U ^ \Dagger = U $.

## <a name="type-parameters"></a>Parametry typu

### <a name="t"></a>'C


### <a name="s"></a>Przeglądarki



## <a name="remarks"></a>Uwagi

Ta `BlockEncoding` implementacja zapewnia właściwości `BlockEncodingReflection` .

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Symulacja. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Symulacja. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)