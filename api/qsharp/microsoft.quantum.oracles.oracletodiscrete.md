---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193849"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


W wyniku operacji reprezentowanej przez firmę Oracle "Black-Box" funkcja zwraca osobne oprogramowanie Oracle, które reprezentuje wielokrotnie powtórzone oprogramowanie Oracle.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Dane wejściowe

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [Jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL

Operacja do exponentiated.



## <a name="output--discreteoracle"></a>Wynik: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Operacja częściowo zastosowana w odniesieniu do "czarnego" "firmy Oracle reprezentującej oprogramowanie Oracle w czasie dyskretnym