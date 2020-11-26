---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201516"
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