---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850097"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="6d187-102">RangeAsIntArray, funkcja</span><span class="sxs-lookup"><span data-stu-id="6d187-102">RangeAsIntArray function</span></span>

<span data-ttu-id="6d187-103">Przestrzeń nazw: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="6d187-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="6d187-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d187-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d187-105">Tworzy tablicę `arr` liczb całkowitych wyliczanych przez początek.. krok.. punktów.</span><span class="sxs-lookup"><span data-stu-id="6d187-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="6d187-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="6d187-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="6d187-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="6d187-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="6d187-108">`Range`Wartości `start..step..end` do przekonwertowania na tablicę.</span><span class="sxs-lookup"><span data-stu-id="6d187-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="6d187-109">Wynik: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6d187-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6d187-110">Nowa tablica liczb całkowitych odpowiadających wartościom powtarzanym przez `range` .</span><span class="sxs-lookup"><span data-stu-id="6d187-110">A new array of integers corresponding to values iterated over by `range`.</span></span>

## <a name="example"></a><span data-ttu-id="6d187-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="6d187-111">Example</span></span>

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```