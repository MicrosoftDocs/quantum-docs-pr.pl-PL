---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718857"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="bc0d2-102">SquareArrayFact, funkcja</span><span class="sxs-lookup"><span data-stu-id="bc0d2-102">SquareArrayFact function</span></span>

<span data-ttu-id="bc0d2-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bc0d2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bc0d2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc0d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc0d2-105">Reprezentuje warunek, którego Dwuwymiarowa tablica ma kształt kwadratowy</span><span class="sxs-lookup"><span data-stu-id="bc0d2-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="bc0d2-106">Opis</span><span class="sxs-lookup"><span data-stu-id="bc0d2-106">Description</span></span>

<span data-ttu-id="bc0d2-107">Ta funkcja potwierdza, że każdy wiersz w tablicy ma tyle elementów jak wiersze (elementy) w tablicy.</span><span class="sxs-lookup"><span data-stu-id="bc0d2-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="bc0d2-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="bc0d2-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="bc0d2-109">Tablica: t [] []</span><span class="sxs-lookup"><span data-stu-id="bc0d2-109">array : 'T[][]</span></span>

<span data-ttu-id="bc0d2-110">Dwuwymiarowa tablica elementów</span><span class="sxs-lookup"><span data-stu-id="bc0d2-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="bc0d2-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bc0d2-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bc0d2-112">Komunikat do wydrukowania, jeśli tablica nie jest tablicą kwadratową</span><span class="sxs-lookup"><span data-stu-id="bc0d2-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="bc0d2-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bc0d2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bc0d2-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="bc0d2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bc0d2-115">'C</span><span class="sxs-lookup"><span data-stu-id="bc0d2-115">'T</span></span>

<span data-ttu-id="bc0d2-116">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="bc0d2-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc0d2-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bc0d2-117">See Also</span></span>

- [<span data-ttu-id="bc0d2-118">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="bc0d2-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)