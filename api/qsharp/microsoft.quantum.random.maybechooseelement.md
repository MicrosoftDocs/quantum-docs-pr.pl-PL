---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722166"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="d9af2-102">MaybeChooseElement, operacja</span><span class="sxs-lookup"><span data-stu-id="d9af2-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="d9af2-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="d9af2-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="d9af2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9af2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9af2-105">Dana Tablica danych i rozkład w jego indeksie, próbuje wybrać element losowo.</span><span class="sxs-lookup"><span data-stu-id="d9af2-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="d9af2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="d9af2-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="d9af2-107">dane: t []</span><span class="sxs-lookup"><span data-stu-id="d9af2-107">data : 'T[]</span></span>

<span data-ttu-id="d9af2-108">Tablica, z której ma zostać wybrany element.</span><span class="sxs-lookup"><span data-stu-id="d9af2-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="d9af2-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="d9af2-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="d9af2-110">Dystrybucja względem indeksów `data` .</span><span class="sxs-lookup"><span data-stu-id="d9af2-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="d9af2-111">Wynik: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="d9af2-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d9af2-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="d9af2-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9af2-113">'C</span><span class="sxs-lookup"><span data-stu-id="d9af2-113">'T</span></span>

