---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842534"
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

## <a name="example"></a>Przykład

`OracleToDiscrete(U)(3, target)` jest równoważne `U(target)` powtórzonym trzykrotnie.