---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827905"
---
# <a name="nearequalityfactd-function"></a>NearEqualityFactD, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Potwierdza, że klasyczna wartość zmiennoprzecinkowa ma oczekiwaną wartość do małej tolerancji o wartości 1e-10.

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--double"></a>rzeczywista: [podwójne](xref:microsoft.quantum.lang-ref.double)

Liczba, która ma zostać sprawdzona.


### <a name="expected--double"></a>Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)

Oczekiwana wartość.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Uwagi

Jest to równoznaczne <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> z stałe odporności na $10 ^ {-10} $.