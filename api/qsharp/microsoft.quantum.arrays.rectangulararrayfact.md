---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845502"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="444ef-102">RectangularArrayFact, funkcja</span><span class="sxs-lookup"><span data-stu-id="444ef-102">RectangularArrayFact function</span></span>

<span data-ttu-id="444ef-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="444ef-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="444ef-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="444ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="444ef-105">Reprezentuje warunek, którego Dwuwymiarowa tablica ma kształt prostokątny</span><span class="sxs-lookup"><span data-stu-id="444ef-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="444ef-106">Opis</span><span class="sxs-lookup"><span data-stu-id="444ef-106">Description</span></span>

<span data-ttu-id="444ef-107">Ta funkcja potwierdza, że każdy wiersz w tablicy ma tę samą długość.</span><span class="sxs-lookup"><span data-stu-id="444ef-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="444ef-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="444ef-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="444ef-109">Tablica: t [] []</span><span class="sxs-lookup"><span data-stu-id="444ef-109">array : 'T[][]</span></span>

<span data-ttu-id="444ef-110">Dwuwymiarowa tablica elementów</span><span class="sxs-lookup"><span data-stu-id="444ef-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="444ef-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="444ef-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="444ef-112">Komunikat do wydrukowania, jeśli tablica nie jest tablicą prostokątną</span><span class="sxs-lookup"><span data-stu-id="444ef-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="444ef-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="444ef-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="444ef-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="444ef-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="444ef-115">'C</span><span class="sxs-lookup"><span data-stu-id="444ef-115">'T</span></span>

<span data-ttu-id="444ef-116">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="444ef-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="444ef-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="444ef-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="444ef-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="444ef-118">See Also</span></span>

- [<span data-ttu-id="444ef-119">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="444ef-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)