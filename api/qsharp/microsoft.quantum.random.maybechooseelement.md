---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856112"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="4a467-102">MaybeChooseElement, operacja</span><span class="sxs-lookup"><span data-stu-id="4a467-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="4a467-103">Przestrzeń nazw: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="4a467-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="4a467-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4a467-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4a467-105">Dana Tablica danych i rozkład w jego indeksie, próbuje wybrać element losowo.</span><span class="sxs-lookup"><span data-stu-id="4a467-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="4a467-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4a467-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="4a467-107">dane: t []</span><span class="sxs-lookup"><span data-stu-id="4a467-107">data : 'T[]</span></span>

<span data-ttu-id="4a467-108">Tablica, z której ma zostać wybrany element.</span><span class="sxs-lookup"><span data-stu-id="4a467-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="4a467-109">indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="4a467-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="4a467-110">Dystrybucja względem indeksów `data` .</span><span class="sxs-lookup"><span data-stu-id="4a467-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="4a467-111">Wynik: ([bool](xref:microsoft.quantum.lang-ref.bool), 't)</span><span class="sxs-lookup"><span data-stu-id="4a467-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a467-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4a467-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a467-113">'C</span><span class="sxs-lookup"><span data-stu-id="4a467-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="4a467-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="4a467-114">Example</span></span>

<span data-ttu-id="4a467-115">Poniższy fragment kodu Q # wybiera Element losowo z tablicy:</span><span class="sxs-lookup"><span data-stu-id="4a467-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```