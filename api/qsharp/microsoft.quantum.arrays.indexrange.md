---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719148"
---
# <a name="indexrange-function"></a><span data-ttu-id="20908-102">IndexRange, funkcja</span><span class="sxs-lookup"><span data-stu-id="20908-102">IndexRange function</span></span>

<span data-ttu-id="20908-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="20908-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="20908-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20908-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20908-105">Dana tablica zwraca zakres przez indeksy tej tablicy, odpowiedni do użycia w pętli for.</span><span class="sxs-lookup"><span data-stu-id="20908-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="20908-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="20908-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="20908-107">Array: "TEle []</span><span class="sxs-lookup"><span data-stu-id="20908-107">array : 'TElement[]</span></span>

<span data-ttu-id="20908-108">Tablica, dla której należy zwrócić zakres indeksów.</span><span class="sxs-lookup"><span data-stu-id="20908-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="20908-109">Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="20908-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="20908-110">Zakres na wszystkie indeksy tablicy.</span><span class="sxs-lookup"><span data-stu-id="20908-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="20908-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="20908-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="20908-112">"TEle</span><span class="sxs-lookup"><span data-stu-id="20908-112">'TElement</span></span>

<span data-ttu-id="20908-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="20908-113">The type of elements of the array.</span></span>