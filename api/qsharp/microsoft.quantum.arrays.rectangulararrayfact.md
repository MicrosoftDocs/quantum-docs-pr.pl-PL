---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220420"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="f698c-102">RectangularArrayFact, funkcja</span><span class="sxs-lookup"><span data-stu-id="f698c-102">RectangularArrayFact function</span></span>

<span data-ttu-id="f698c-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f698c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f698c-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f698c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f698c-105">Reprezentuje warunek, którego Dwuwymiarowa tablica ma kształt prostokątny</span><span class="sxs-lookup"><span data-stu-id="f698c-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="f698c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="f698c-106">Description</span></span>

<span data-ttu-id="f698c-107">Ta funkcja potwierdza, że każdy wiersz w tablicy ma tę samą długość.</span><span class="sxs-lookup"><span data-stu-id="f698c-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="f698c-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f698c-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="f698c-109">Tablica: t [] []</span><span class="sxs-lookup"><span data-stu-id="f698c-109">array : 'T[][]</span></span>

<span data-ttu-id="f698c-110">Dwuwymiarowa tablica elementów</span><span class="sxs-lookup"><span data-stu-id="f698c-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="f698c-111">komunikat: [ciąg](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="f698c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="f698c-112">Komunikat do wydrukowania, jeśli tablica nie jest tablicą prostokątną</span><span class="sxs-lookup"><span data-stu-id="f698c-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="f698c-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f698c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f698c-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f698c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f698c-115">'C</span><span class="sxs-lookup"><span data-stu-id="f698c-115">'T</span></span>

<span data-ttu-id="f698c-116">Typ każdego elementu `array` .</span><span class="sxs-lookup"><span data-stu-id="f698c-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="f698c-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f698c-117">See Also</span></span>

- [<span data-ttu-id="f698c-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="f698c-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)