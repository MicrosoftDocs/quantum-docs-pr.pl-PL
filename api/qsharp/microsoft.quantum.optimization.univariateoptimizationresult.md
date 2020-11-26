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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="e38c5-102">UnivariateOptimizationResult typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="e38c5-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="e38c5-103">Przestrzeń nazw: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="e38c5-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="e38c5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e38c5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e38c5-105">Reprezentuje wynik optymalizacji funkcji univariate.</span><span class="sxs-lookup"><span data-stu-id="e38c5-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="e38c5-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="e38c5-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="e38c5-107">Koordynuj: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e38c5-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e38c5-108">Dane wejściowe, w których znaleziono optymalny.</span><span class="sxs-lookup"><span data-stu-id="e38c5-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="e38c5-109">Wartość: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e38c5-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e38c5-110">Wartość zwracana przez funkcję jest optymalna.</span><span class="sxs-lookup"><span data-stu-id="e38c5-110">Value returned by the function at its optimum.</span></span>