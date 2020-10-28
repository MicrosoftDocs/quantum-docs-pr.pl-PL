---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719280"
---
# <a name="exclude-function"></a><span data-ttu-id="087f7-102">Exclude — funkcja</span><span class="sxs-lookup"><span data-stu-id="087f7-102">Exclude function</span></span>

<span data-ttu-id="087f7-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="087f7-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="087f7-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="087f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="087f7-105">Zwraca tablicę zawierającą elementy innej tablicy, z wyłączeniem elementów na danej liście indeksów.</span><span class="sxs-lookup"><span data-stu-id="087f7-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="087f7-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="087f7-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="087f7-107">Usuń: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="087f7-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="087f7-108">Tablica indeksów wskazująca, które elementy powinny być wykluczone z danych wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="087f7-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="087f7-109">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="087f7-109">array : 'T[]</span></span>

<span data-ttu-id="087f7-110">Tablica, z której są pobierane wartości w tablicy wyjściowej.</span><span class="sxs-lookup"><span data-stu-id="087f7-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="087f7-111">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="087f7-111">Output : 'T[]</span></span>

<span data-ttu-id="087f7-112">Tablica, `output` taka jak `output[0]` pierwszy element, `array` którego indeks nie pojawia się w, na `remove` przykład to `output[1]` drugi element, i tak dalej.</span><span class="sxs-lookup"><span data-stu-id="087f7-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="087f7-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="087f7-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="087f7-114">'C</span><span class="sxs-lookup"><span data-stu-id="087f7-114">'T</span></span>

<span data-ttu-id="087f7-115">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="087f7-115">The type of the array elements.</span></span>