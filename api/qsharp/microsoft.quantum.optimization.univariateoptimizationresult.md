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
# <a name="univariateoptimizationresult-user-defined-type"></a><span data-ttu-id="693e2-102">UnivariateOptimizationResult typ zdefiniowany przez użytkownika</span><span class="sxs-lookup"><span data-stu-id="693e2-102">UnivariateOptimizationResult user defined type</span></span>

<span data-ttu-id="693e2-103">Przestrzeń nazw: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="693e2-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="693e2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="693e2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="693e2-105">Reprezentuje wynik optymalizacji funkcji univariate.</span><span class="sxs-lookup"><span data-stu-id="693e2-105">Represents the result of optimizing a univariate function.</span></span>

```qsharp

newtype UnivariateOptimizationResult = (Coordinate : Double, Value : Double);
```



## <a name="named-items"></a><span data-ttu-id="693e2-106">Nazwane elementy</span><span class="sxs-lookup"><span data-stu-id="693e2-106">Named Items</span></span>

### <a name="coordinate--double"></a><span data-ttu-id="693e2-107">Koordynuj: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="693e2-107">Coordinate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="693e2-108">Dane wejściowe, w których znaleziono optymalny.</span><span class="sxs-lookup"><span data-stu-id="693e2-108">Input at which an optimum was found.</span></span>
### <a name="value--double"></a><span data-ttu-id="693e2-109">Wartość: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="693e2-109">Value : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="693e2-110">Wartość zwracana przez funkcję jest optymalna.</span><span class="sxs-lookup"><span data-stu-id="693e2-110">Value returned by the function at its optimum.</span></span>