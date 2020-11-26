---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: ApproximateQFT, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 97a410133e80cc5bffc810e9d6455baaee32364b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207704"
---
# <a name="approximateqft-operation"></a>ApproximateQFT, operacja

Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Zastosuj przybliżoną transformację Quantum Fouriera (AQFT) do rejestru Quantum.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Dane wejściowe

### <a name="a--int"></a>Odp.: [int](xref:microsoft.quantum.lang-ref.int)

Przybliżony parametr, który określa, na którym poziomie kontrolowane są obroty Z osi Z, które występują w obwodzie QFT.

Parametr przybliżenia a określa poziom oczyszczania obrotów Z, czyli ∈ {0.. n} i wszystkie rotacje Z 2π/2K, gdzie k>a są usuwane z obwodu QFT. Wiadomo, że w przypadku k >= log ₂ (n) + log ₂ (1/ε) + 3 jeden może być powiązany | | QFT-AQFT | |<ε.


### <a name="qs--bigendian"></a>QS: [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Rejestr Quantum o n qubits, do którego jest stosowana Przybliżona transformacja Quantum Fouriera.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

AQFT wymaga bram do rotacji z 2π/2K i Hadamard.

Założono, że dane wejściowe i wyjściowe są kodowane w kodowaniu big endian.

## <a name="references"></a>Odwołania

- [*M. Roetteler, th. Beth*, Zastosuj. algebry aparatu. gmin. Comput. 19 (3): 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* ArXiv: Quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)