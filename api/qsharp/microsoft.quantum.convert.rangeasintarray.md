---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713365"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="4bf5a-102">RangeAsIntArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="4bf5a-102">RangeAsIntArray function</span></span>

<span data-ttu-id="4bf5a-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="4bf5a-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="4bf5a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4bf5a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4bf5a-105">Tworzy tablicę `arr` liczb całkowitych wyliczanych przez początek.. krok.. punktów.</span><span class="sxs-lookup"><span data-stu-id="4bf5a-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="4bf5a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4bf5a-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="4bf5a-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4bf5a-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="4bf5a-108">`Range`Wartości `start..step..end` do przekonwertowania na tablicę.</span><span class="sxs-lookup"><span data-stu-id="4bf5a-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="4bf5a-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="4bf5a-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="4bf5a-110">Nowa tablica liczb całkowitych odpowiadających wartościom powtarzanym przez `range` .</span><span class="sxs-lookup"><span data-stu-id="4bf5a-110">A new array of integers corresponding to values iterated over by `range`.</span></span>