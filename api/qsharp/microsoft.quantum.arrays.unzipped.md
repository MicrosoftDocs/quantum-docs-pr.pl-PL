---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funkcja unspakowane
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: aee1d48c9e0a1f104040bc56c78fdbb8bc4d34ba
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219961"
---
# <a name="unzipped-function"></a><span data-ttu-id="8f341-102">Funkcja unspakowane</span><span class="sxs-lookup"><span data-stu-id="8f341-102">Unzipped function</span></span>

<span data-ttu-id="8f341-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8f341-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8f341-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f341-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f341-105">Dana Tablica 2-krotek zwraca spójną kolekcję dwóch tablic, z których każda zawiera elementy krotek tablicy wejściowej.</span><span class="sxs-lookup"><span data-stu-id="8f341-105">Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.</span></span>

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a><span data-ttu-id="8f341-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f341-106">Input</span></span>

### <a name="arr--tu"></a><span data-ttu-id="8f341-107">ARR: ('T, ' U) []</span><span class="sxs-lookup"><span data-stu-id="8f341-107">arr : ('T,'U)[]</span></span>

<span data-ttu-id="8f341-108">Tablica zawierająca 2-krotek</span><span class="sxs-lookup"><span data-stu-id="8f341-108">An array containing 2-tuples</span></span>



## <a name="output--tu"></a><span data-ttu-id="8f341-109">Wynik: (t [], ' U [])</span><span class="sxs-lookup"><span data-stu-id="8f341-109">Output : ('T[],'U[])</span></span>

<span data-ttu-id="8f341-110">Dwie tablice, pierwszy zawierający wszystkie pierwsze elementy spójnych krotek, drugi, zawierający wszystkie pozostałe elementy spójnych krotek.</span><span class="sxs-lookup"><span data-stu-id="8f341-110">Two arrays, the first one containing all first elements of the input tuples, the second one containing all second elements of the input tuples.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8f341-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8f341-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f341-112">'C</span><span class="sxs-lookup"><span data-stu-id="8f341-112">'T</span></span>

<span data-ttu-id="8f341-113">Typ pierwszego elementu w każdej kolekcji</span><span class="sxs-lookup"><span data-stu-id="8f341-113">The type of the first element in each tuple</span></span>
### <a name="u"></a><span data-ttu-id="8f341-114">' U</span><span class="sxs-lookup"><span data-stu-id="8f341-114">'U</span></span>

<span data-ttu-id="8f341-115">Typ drugiego elementu w każdej kolekcji</span><span class="sxs-lookup"><span data-stu-id="8f341-115">The type of the second element in each tuple</span></span>

## <a name="see-also"></a><span data-ttu-id="8f341-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8f341-116">See Also</span></span>

- [<span data-ttu-id="8f341-117">Microsoft.Quantum.Arrays.ZipPED</span><span class="sxs-lookup"><span data-stu-id="8f341-117">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)