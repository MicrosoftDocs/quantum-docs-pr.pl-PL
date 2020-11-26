---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214011"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="17706-102">RangeAsIntArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="17706-102">RangeAsIntArray function</span></span>

<span data-ttu-id="17706-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="17706-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="17706-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17706-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17706-105">Tworzy tablicę `arr` liczb całkowitych wyliczanych przez początek.. krok.. punktów.</span><span class="sxs-lookup"><span data-stu-id="17706-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="17706-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="17706-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="17706-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="17706-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="17706-108">`Range`Wartości `start..step..end` do przekonwertowania na tablicę.</span><span class="sxs-lookup"><span data-stu-id="17706-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="17706-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="17706-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="17706-110">Nowa tablica liczb całkowitych odpowiadających wartościom powtarzanym przez `range` .</span><span class="sxs-lookup"><span data-stu-id="17706-110">A new array of integers corresponding to values iterated over by `range`.</span></span>