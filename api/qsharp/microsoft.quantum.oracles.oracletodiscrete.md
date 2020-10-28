---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724247"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Package [](https://nuget.org/packages/)


W wyniku operacji reprezentowanej przez firmę Oracle "Black-Box" funkcja zwraca osobne oprogramowanie Oracle, które reprezentuje wielokrotnie powtórzone oprogramowanie Oracle.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Dane wejściowe

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => skorygowanie [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL

Operacja do exponentiated.



## <a name="output--discreteoracle"></a>Wynik: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operacja częściowo zastosowana w odniesieniu do "czarnego" "firmy Oracle reprezentującej oprogramowanie Oracle w czasie dyskretnym