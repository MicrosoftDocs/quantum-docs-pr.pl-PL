---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710943"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="26ffa-102">TransformedContinuousDistribution, funkcja</span><span class="sxs-lookup"><span data-stu-id="26ffa-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="26ffa-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="26ffa-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="26ffa-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26ffa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26ffa-105">Pod kątem ciągłej dystrybucji program zwraca nową dystrybucję, która przekształca oryginał przez daną funkcję.</span><span class="sxs-lookup"><span data-stu-id="26ffa-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="26ffa-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="26ffa-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="26ffa-107">transformacja: [podwójne](xref:microsoft.quantum.lang-ref.double) -> [podwójne](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="26ffa-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="26ffa-108">Funkcja, która przekształca variates oryginalnej dystrybucji do przekształconej dystrybucji.</span><span class="sxs-lookup"><span data-stu-id="26ffa-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="26ffa-109">dystrybucja: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="26ffa-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="26ffa-110">Oryginalna dystrybucja, która ma zostać przekształcona.</span><span class="sxs-lookup"><span data-stu-id="26ffa-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="26ffa-111">Wynik: [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="26ffa-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="26ffa-112">Nowa dystrybucja odnosząca się do `distribution` transformacji podawanej przez `transform` .</span><span class="sxs-lookup"><span data-stu-id="26ffa-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>