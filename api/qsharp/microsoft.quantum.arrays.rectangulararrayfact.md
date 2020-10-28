---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718920"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="e8ba0-102">RectangularArrayFact, funkcja</span><span class="sxs-lookup"><span data-stu-id="e8ba0-102">RectangularArrayFact function</span></span>

<span data-ttu-id="e8ba0-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8ba0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8ba0-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8ba0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8ba0-105">Reprezentuje warunek, którego Dwuwymiarowa tablica ma kształt prostokątny</span><span class="sxs-lookup"><span data-stu-id="e8ba0-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="e8ba0-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e8ba0-106">Description</span></span>

<span data-ttu-id="e8ba0-107">Ta funkcja potwierdza, że każdy wiersz w tablicy ma tę samą długość.</span><span class="sxs-lookup"><span data-stu-id="e8ba0-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="e8ba0-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e8ba0-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e8ba0-109">Tablica: t [] []</span><span class="sxs-lookup"><span data-stu-id="e8ba0-109">array : 'T[][]</span></span>

<span data-ttu-id="e8ba0-110">Dwuwymiarowa tablica elementów</span><span class="sxs-lookup"><span data-stu-id="e8ba0-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="e8ba0-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e8ba0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e8ba0-112">Komunikat do wydrukowania, jeśli tablica nie jest tablicą prostokątną</span><span class="sxs-lookup"><span data-stu-id="e8ba0-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="e8ba0-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e8ba0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e8ba0-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e8ba0-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8ba0-115">'C</span><span class="sxs-lookup"><span data-stu-id="e8ba0-115">'T</span></span>

<span data-ttu-id="e8ba0-116">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="e8ba0-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8ba0-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e8ba0-117">See Also</span></span>

- [<span data-ttu-id="e8ba0-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="e8ba0-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)