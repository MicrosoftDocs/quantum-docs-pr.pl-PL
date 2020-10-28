---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: ef9740f1867cee3c79a7ec0bf90f2c2f4b39ad28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725577"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Symulacja](xref:Microsoft.Quantum.Simulation)

Package [](https://nuget.org/packages/)


Konwertuje odbicie w kodowaniu bloku w przeszukiwaniu Quantum.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Opis

W `BlockEncodingReflection` odniesieniu do jednostki $U $, która koduje część operatora $H $ Interest, konwertuje ją na przeszukiwanie quantum $W $ zawierający spektrum $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.

## <a name="input"></a>Dane wejściowe

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`$U jednostkowe $ mają być konwertowane do przeszukiwania Quantum.



## <a name="output--qubitqubit--unit-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Proces Quantum przeprowadzi $W $ wspólnie z rejestrami `a` i `s` ten blok kodu $H $ i zawiera zakres $ \Pm e ^ {\Pm i\sin ^ {-1} (H)} $.

## <a name="references"></a>Dokumentacja

- Symulacja hamiltonian przez Qubitization Guang przerywają Hao Low, Tomasz L. Czuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Zobacz też

- [Microsoft. Quantum. Symulacja. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Symulacja. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)