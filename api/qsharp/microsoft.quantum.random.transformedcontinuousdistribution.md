---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226268"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="5a5e4-102">TransformedContinuousDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="5a5e4-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="5a5e4-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="5a5e4-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="5a5e4-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5a5e4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5a5e4-105">Pod kątem ciągłej dystrybucji program zwraca nową dystrybucję, która przekształca oryginał przez daną funkcję.</span><span class="sxs-lookup"><span data-stu-id="5a5e4-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="5a5e4-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5a5e4-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="5a5e4-107">transformacja: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5a5e4-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5a5e4-108">Funkcja, która przekształca variates oryginalnej dystrybucji do przekształconej dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="5a5e4-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="5a5e4-109">dystrybucja: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="5a5e4-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="5a5e4-110">Oryginalna dystrybucja, która ma zostać przekształcona.</span><span class="sxs-lookup"><span data-stu-id="5a5e4-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="5a5e4-111">Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="5a5e4-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="5a5e4-112">Nowa dystrybucja odnosząca się do `distribution` transformacji podawanej przez `transform` .</span><span class="sxs-lookup"><span data-stu-id="5a5e4-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>