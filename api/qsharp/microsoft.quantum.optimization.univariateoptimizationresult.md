---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult typ zdefiniowany przez użytkownika
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: 0bcdbda5586181f965297cb2a398d766f9c6fabb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194036"
---
# <a name="univariateoptimizationresult-user-defined-type"></a>UnivariateOptimizationResult typ zdefiniowany przez użytkownika

Przestrzeń nazw: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)

Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Reprezentuje wynik optymalizacji funkcji univariate.

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a>Nazwane elementy

### <a name="coordinate--double"></a>Koordynuj: [Double](xref:microsoft.quantum.lang-ref.double)

Dane wejściowe, w których znaleziono optymalny.
### <a name="value--double"></a>Wartość: [Double](xref:microsoft.quantum.lang-ref.double)

Wartość zwracana przez funkcję jest optymalna.