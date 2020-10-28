---
uid: Microsoft.Quantum.Arrays.Excluding
title: Wyłączanie funkcji
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 8848c6e89da50efb4f7550168f1757b25a214a24
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719277"
---
# <a name="excluding-function"></a><span data-ttu-id="b1dad-102">Wyłączanie funkcji</span><span class="sxs-lookup"><span data-stu-id="b1dad-102">Excluding function</span></span>

<span data-ttu-id="b1dad-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b1dad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b1dad-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b1dad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b1dad-105">Zwraca tablicę zawierającą elementy innej tablicy, z wyłączeniem elementów na danej liście indeksów.</span><span class="sxs-lookup"><span data-stu-id="b1dad-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b1dad-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b1dad-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="b1dad-107">Usuń: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b1dad-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b1dad-108">Tablica indeksów wskazująca, które elementy powinny być wykluczone z danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="b1dad-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="b1dad-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="b1dad-109">array : 'T[]</span></span>

<span data-ttu-id="b1dad-110">Tablica, z której są pobierane wartości w tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="b1dad-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="b1dad-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="b1dad-111">Output : 'T[]</span></span>

<span data-ttu-id="b1dad-112">Tablica, `output` taka jak `output[0]` pierwszy element, `array` którego indeks nie pojawia się w, na `remove` przykład to `output[1]` drugi element, i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="b1dad-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b1dad-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b1dad-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1dad-114">'C</span><span class="sxs-lookup"><span data-stu-id="b1dad-114">'T</span></span>

<span data-ttu-id="b1dad-115">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="b1dad-115">The type of the array elements.</span></span>