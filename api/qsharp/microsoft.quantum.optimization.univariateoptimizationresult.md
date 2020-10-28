---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult typ zdefiniowany przez użytkownika
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: c8aa91bbdc9e9e9bb4d110b470ff2041f9460a38
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724322"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Package [](https://nuget.org/packages/)


Reprezentuje wynik optymalizacji funkcji univariate.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="coordinate--double"></a>Koordynuj: [Double](xref:microsoft.quantum.lang-ref.double)

Dane wejściowe, w których znaleziono optymalny.
### <a name="value--double"></a>Wartość: [Double](xref:microsoft.quantum.lang-ref.double)

Wartość zwracana przez funkcję jest optymalna.