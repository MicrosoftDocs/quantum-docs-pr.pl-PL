---
uid: Microsoft.Quantum.Optimization.LocalUnivariateMinimum
title: LocalUnivariateMinimum, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Optimization
qsharp.name: LocalUnivariateMinimum
qsharp.summary: Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.
ms.openlocfilehash: c2d094a6d0e0c7cecb249cd517995e11dff3d3b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854612"
---
# <a name="localunivariateminimum-function"></a><span data-ttu-id="2d121-102">LocalUnivariateMinimum, funkcja</span><span class="sxs-lookup"><span data-stu-id="2d121-102">LocalUnivariateMinimum function</span></span>

<span data-ttu-id="2d121-103">Przestrzeń nazw: [Microsoft. Quantum. Optimization](xref:Microsoft.Quantum.Optimization)</span><span class="sxs-lookup"><span data-stu-id="2d121-103">Namespace: [Microsoft.Quantum.Optimization](xref:Microsoft.Quantum.Optimization)</span></span>

<span data-ttu-id="2d121-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d121-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d121-105">Zwraca wartość minimalną dla funkcji univariate w przedziale czasu, korzystając z wyszukiwanego interwału.</span><span class="sxs-lookup"><span data-stu-id="2d121-105">Returns the local minimum for a univariate function over a bounded interval, using a golden interval search.</span></span>

```qsharp
function LocalUnivariateMinimum (fn : (Double -> Double), bounds : (Double, Double), tolerance : Double) : Microsoft.Quantum.Optimization.UnivariateOptimizationResult
```


## <a name="input"></a><span data-ttu-id="2d121-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2d121-106">Input</span></span>

### <a name="fn--double---double"></a><span data-ttu-id="2d121-107">fn: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2d121-107">fn : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2d121-108">Funkcja univariate do zminimalizowania.</span><span class="sxs-lookup"><span data-stu-id="2d121-108">The univariate function to be minimized.</span></span>


### <a name="bounds--doubledouble"></a><span data-ttu-id="2d121-109">granice: ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="2d121-109">bounds : ([Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="2d121-110">Interwał, w którym ma zostać znalezione lokalne minimum.</span><span class="sxs-lookup"><span data-stu-id="2d121-110">The interval in which the local minimum is to be found.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="2d121-111">Tolerancja: [Podwójna precyzja](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="2d121-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="2d121-112">Dokładność w danych wejściowych funkcji, która ma być tolerowana.</span><span class="sxs-lookup"><span data-stu-id="2d121-112">The accuracy in the function input to be tolerated.</span></span>
<span data-ttu-id="2d121-113">Wyszukiwanie lokalnego Optima będzie kontynuowane, dopóki interwał nie będzie krótszy niż ta tolerancja.</span><span class="sxs-lookup"><span data-stu-id="2d121-113">The search for local optima will continue until the interval is smaller in width than this tolerance.</span></span>



## <a name="output--univariateoptimizationresult"></a><span data-ttu-id="2d121-114">Wynik: [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span><span class="sxs-lookup"><span data-stu-id="2d121-114">Output : [UnivariateOptimizationResult](xref:Microsoft.Quantum.Optimization.UnivariateOptimizationResult)</span></span>

<span data-ttu-id="2d121-115">Lokalny Optima danej funkcji, znajdujący się w obrębie określonych granic.</span><span class="sxs-lookup"><span data-stu-id="2d121-115">A local optima of the given function, located within the given bounds.</span></span>