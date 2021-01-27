---
uid: Microsoft.Quantum.Optimization.UnivariateOptimizationResult
title: UnivariateOptimizationResult typ zdefiniowany przez użytkownika
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: UnivariateOptimizationResult
qsharp.summary: Represents the result of optimizing a univariate function.
ms.openlocfilehash: cc54c0035796aac86482e8a3a6896ceb197c7cfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854565"
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