---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220947"
---
# <a name="indexrange-function"></a><span data-ttu-id="37a23-102">IndexRange, funkcja</span><span class="sxs-lookup"><span data-stu-id="37a23-102">IndexRange function</span></span>

<span data-ttu-id="37a23-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="37a23-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="37a23-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="37a23-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="37a23-105">Dana tablica zwraca zakres przez indeksy tej tablicy, odpowiedni do użycia w pętli for.</span><span class="sxs-lookup"><span data-stu-id="37a23-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="37a23-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="37a23-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="37a23-107">Array: "TEle []</span><span class="sxs-lookup"><span data-stu-id="37a23-107">array : 'TElement[]</span></span>

<span data-ttu-id="37a23-108">Tablica, dla której należy zwrócić zakres indeksów.</span><span class="sxs-lookup"><span data-stu-id="37a23-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="37a23-109">Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="37a23-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="37a23-110">Zakres na wszystkie indeksy tablicy.</span><span class="sxs-lookup"><span data-stu-id="37a23-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="37a23-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="37a23-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="37a23-112">"TEle</span><span class="sxs-lookup"><span data-stu-id="37a23-112">'TElement</span></span>

<span data-ttu-id="37a23-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="37a23-113">The type of elements of the array.</span></span>