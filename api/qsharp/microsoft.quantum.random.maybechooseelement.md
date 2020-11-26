---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192863"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="a9592-102">MaybeChooseElement, operacja</span><span class="sxs-lookup"><span data-stu-id="a9592-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="a9592-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a9592-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a9592-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a9592-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a9592-105">Dana Tablica danych i rozkład w jego indeksie, próbuje wybrać element losowo.</span><span class="sxs-lookup"><span data-stu-id="a9592-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="a9592-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a9592-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="a9592-107">dane: t []</span><span class="sxs-lookup"><span data-stu-id="a9592-107">data : 'T[]</span></span>

<span data-ttu-id="a9592-108">Tablica, z której ma zostać wybrany element.</span><span class="sxs-lookup"><span data-stu-id="a9592-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="a9592-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="a9592-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="a9592-110">Dystrybucja względem indeksów `data` .</span><span class="sxs-lookup"><span data-stu-id="a9592-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="a9592-111">Wynik: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="a9592-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a9592-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a9592-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9592-113">'C</span><span class="sxs-lookup"><span data-stu-id="a9592-113">'T</span></span>

