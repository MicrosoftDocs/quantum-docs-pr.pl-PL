---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845778"
---
# <a name="indexrange-function"></a><span data-ttu-id="f1b4e-102">IndexRange, funkcja</span><span class="sxs-lookup"><span data-stu-id="f1b4e-102">IndexRange function</span></span>

<span data-ttu-id="f1b4e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f1b4e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f1b4e-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f1b4e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f1b4e-105">Dana tablica zwraca zakres przez indeksy tej tablicy, odpowiedni do użycia w pętli for.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="f1b4e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f1b4e-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="f1b4e-107">Array: "TEle []</span><span class="sxs-lookup"><span data-stu-id="f1b4e-107">array : 'TElement[]</span></span>

<span data-ttu-id="f1b4e-108">Tablica, dla której należy zwrócić zakres indeksów.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="f1b4e-109">Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f1b4e-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f1b4e-110">Zakres na wszystkie indeksy tablicy.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f1b4e-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f1b4e-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="f1b4e-112">"TEle</span><span class="sxs-lookup"><span data-stu-id="f1b4e-112">'TElement</span></span>

<span data-ttu-id="f1b4e-113">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="f1b4e-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="f1b4e-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="f1b4e-114">Example</span></span>

<span data-ttu-id="f1b4e-115">Następujące `for` pętle są równoważne:</span><span class="sxs-lookup"><span data-stu-id="f1b4e-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```