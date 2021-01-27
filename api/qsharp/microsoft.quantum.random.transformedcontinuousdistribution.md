---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 353442a4245a9e20bb1e4c46d2e8a84d4c9534b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857769"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="069bc-102">TransformedContinuousDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="069bc-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="069bc-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="069bc-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="069bc-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="069bc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="069bc-105">Pod kątem ciągłej dystrybucji program zwraca nową dystrybucję, która przekształca oryginał przez daną funkcję.</span><span class="sxs-lookup"><span data-stu-id="069bc-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="069bc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="069bc-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="069bc-107">transformacja: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="069bc-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="069bc-108">Funkcja, która przekształca variates oryginalnej dystrybucji do przekształconej dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="069bc-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="069bc-109">dystrybucja: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="069bc-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="069bc-110">Oryginalna dystrybucja, która ma zostać przekształcona.</span><span class="sxs-lookup"><span data-stu-id="069bc-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="069bc-111">Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="069bc-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="069bc-112">Nowa dystrybucja odnosząca się do `distribution` transformacji podawanej przez `transform` .</span><span class="sxs-lookup"><span data-stu-id="069bc-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>

## <a name="example"></a><span data-ttu-id="069bc-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="069bc-113">Example</span></span>

<span data-ttu-id="069bc-114">Następujące dwa dystrybucje są identyczne:</span><span class="sxs-lookup"><span data-stu-id="069bc-114">The following two distributions are identical:</span></span>

```qsharp
let dist1 = ContinuousUniformDistribution(1.0, 2.0);
let dist2 = TransformedContinuousDistribution(
    PlusD(1.0, _),
    ContinuousUniformDistribution(0.0, 1.0)
);
```