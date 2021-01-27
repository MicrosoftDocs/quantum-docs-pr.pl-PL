---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkcja unspakowane
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 7eea7982721dc596b8660be5f3634df71b1ddf95
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845381"
---
# <a name="unzipped-function"></a><span data-ttu-id="704ea-102">Funkcja unspakowane</span><span class="sxs-lookup"><span data-stu-id="704ea-102">Unzipped function</span></span>

<span data-ttu-id="704ea-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="704ea-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="704ea-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="704ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="704ea-105">Dana Tablica 2-krotek zwraca spójną kolekcję dwóch tablic, z których każda zawiera elementy krotek tablicy wejściowej.</span><span class="sxs-lookup"><span data-stu-id="704ea-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="704ea-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="704ea-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="704ea-107">ARR: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="704ea-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="704ea-108">Tablica zawierająca 2-krotek</span><span class="sxs-lookup"><span data-stu-id="704ea-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="704ea-109">Wynik: (t [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="704ea-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="704ea-110">Dwie tablice, pierwszy zawierający wszystkie pierwsze elementy spójnych krotek, drugi, zawierający wszystkie pozostałe elementy spójnych krotek.</span><span class="sxs-lookup"><span data-stu-id="704ea-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="704ea-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="704ea-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="704ea-112">'C</span><span class="sxs-lookup"><span data-stu-id="704ea-112">'T</span></span>

<span data-ttu-id="704ea-113">Typ pierwszego elementu w każdej kolekcji</span><span class="sxs-lookup"><span data-stu-id="704ea-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="704ea-114">' U</span><span class="sxs-lookup"><span data-stu-id="704ea-114">'U</span></span>

<span data-ttu-id="704ea-115">Typ drugiego elementu w każdej kolekcji</span><span class="sxs-lookup"><span data-stu-id="704ea-115">The type of the second element in each tuple</span></span>

## <a name="example"></a><span data-ttu-id="704ea-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="704ea-116">Example</span></span>

```qsharp
// split is same as ([6, 5, 5, 3, 2, 1], [true, false, false, false, true, false])
let split = Unzipped([(6, true), (5, false), (5, false), (3, false), (2, true), (1, false)]);
```

## <a name="see-also"></a><span data-ttu-id="704ea-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="704ea-117">See Also</span></span>

- [<span data-ttu-id="704ea-118">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="704ea-118">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)