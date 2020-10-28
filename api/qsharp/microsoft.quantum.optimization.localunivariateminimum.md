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
# <a name="localunivariateminimum-function"></a><span data-ttu-id="6fcc0-102">LocalUnivariateMinimum, funkcja</span><span class="sxs-lookup"><span data-stu-id="6fcc0-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="6fcc0-103">Przestrzeń nazw: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="6fcc0-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="6fcc0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6fcc0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6fcc0-105">Zwraca wartość minimalną dla funkcji univariate w przedziale czasu, korzystając z wyszukiwanego interwału.</span><span class="sxs-lookup"><span data-stu-id="6fcc0-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="6fcc0-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6fcc0-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="6fcc0-107">fn: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6fcc0-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6fcc0-108">Funkcja univariate do zminimalizowania.</span><span class="sxs-lookup"><span data-stu-id="6fcc0-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="6fcc0-109">granice: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="6fcc0-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="6fcc0-110">Interwał, w którym ma zostać znalezione lokalne minimum.</span><span class="sxs-lookup"><span data-stu-id="6fcc0-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="6fcc0-111">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6fcc0-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6fcc0-112">Dokładność w danych wejściowych funkcji, która ma być tolerowana.</span><span class="sxs-lookup"><span data-stu-id="6fcc0-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="6fcc0-113">Wyszukiwanie lokalnego Optima będzie kontynuowane, dopóki interwał nie będzie krótszy niż ta tolerancja.</span><span class="sxs-lookup"><span data-stu-id="6fcc0-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="6fcc0-114">Wynik: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="6fcc0-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="6fcc0-115">Lokalny Optima danej funkcji, znajdujący się w obrębie określonych granic.</span><span class="sxs-lookup"><span data-stu-id="6fcc0-115">A local optima of the given function, located within the given bounds.</span></span>