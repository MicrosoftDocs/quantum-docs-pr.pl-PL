---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkcja unspakowane
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718788"
---
# <a name="unzipped-function"></a><span data-ttu-id="a0f21-102">Funkcja unspakowane</span><span class="sxs-lookup"><span data-stu-id="a0f21-102">Unzipped function</span></span>

<span data-ttu-id="a0f21-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a0f21-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a0f21-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a0f21-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a0f21-105">Dana Tablica 2-krotek zwraca spójną kolekcję dwóch tablic, z których każda zawiera elementy krotek tablicy wejściowej.</span><span class="sxs-lookup"><span data-stu-id="a0f21-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="a0f21-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a0f21-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="a0f21-107">ARR: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="a0f21-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="a0f21-108">Tablica zawierająca 2-krotek</span><span class="sxs-lookup"><span data-stu-id="a0f21-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="a0f21-109">Wynik: (t [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="a0f21-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="a0f21-110">Dwie tablice, pierwszy zawierający wszystkie pierwsze elementy spójnych krotek, drugi, zawierający wszystkie pozostałe elementy spójnych krotek.</span><span class="sxs-lookup"><span data-stu-id="a0f21-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a0f21-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a0f21-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a0f21-112">'C</span><span class="sxs-lookup"><span data-stu-id="a0f21-112">'T</span></span>

<span data-ttu-id="a0f21-113">Typ pierwszego elementu w każdej kolekcji</span><span class="sxs-lookup"><span data-stu-id="a0f21-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="a0f21-114">' U</span><span class="sxs-lookup"><span data-stu-id="a0f21-114">'U</span></span>

<span data-ttu-id="a0f21-115">Typ drugiego elementu w każdej kolekcji</span><span class="sxs-lookup"><span data-stu-id="a0f21-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="a0f21-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a0f21-116">See Also</span></span>

- [<span data-ttu-id="a0f21-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="a0f21-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)