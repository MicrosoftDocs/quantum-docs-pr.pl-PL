---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201720"
---
# <a name="equalitywithintolerancefact-function"></a>EqualityWithinToleranceFact, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje zastrzeżenie, że klasyczna wartość zmiennoprzecinkowa ma oczekiwaną wartość do odporności absolutnej.

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a>Dane wejściowe

### <a name="actual--double"></a>rzeczywista: [podwójne](xref:microsoft.quantum.lang-ref.double)

Liczba, która ma zostać sprawdzona.


### <a name="expected--double"></a>Oczekiwano: [Double](xref:microsoft.quantum.lang-ref.double)

Oczekiwana wartość.


### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Absolutna tolerancja różnicy między wartością rzeczywistą i oczekiwaną.



## <a name="output--unit"></a>Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)

