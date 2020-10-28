---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: 3b09af88bbed20a392768d005e5e9567b3bb7022
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711018"
---
# <a name="localunivariateminimum-function"></a>LocalUnivariateMinimum, funkcja

Przestrzeń nazw: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Package [](https://nuget.org/packages/)


Zwraca wartość minimalną dla funkcji univariate w przedziale czasu, korzystając z wyszukiwanego interwału.

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a>Dane wejściowe

### <a name="fn--double---double"></a>fn: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)

Funkcja univariate do zminimalizowania.


### <a name="bounds--doubledouble"></a>granice: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))

Interwał, w którym ma zostać znalezione lokalne minimum.


### <a name="tolerance--double"></a>Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)

Dokładność w danych wejściowych funkcji, która ma być tolerowana.
Wyszukiwanie lokalnego Optima będzie kontynuowane, dopóki interwał nie będzie krótszy niż ta tolerancja.



## <a name="output--univariateoptimizationresult"></a>Wynik: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)

Lokalny Optima danej funkcji, znajdujący się w obrębie określonych granic.