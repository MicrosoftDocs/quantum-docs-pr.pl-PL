---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713160"
---
# <a name="rangestep-function"></a><span data-ttu-id="f546a-102">RangeStep, funkcja</span><span class="sxs-lookup"><span data-stu-id="f546a-102">RangeStep function</span></span>

<span data-ttu-id="f546a-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="f546a-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="f546a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f546a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f546a-105">Zwraca liczbę całkowitą określającą sposób obliczania następnej wartości zakresu.</span><span class="sxs-lookup"><span data-stu-id="f546a-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="f546a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f546a-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="f546a-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f546a-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="f546a-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f546a-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f546a-109">Zdefiniowana wartość kroku danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="f546a-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="f546a-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="f546a-110">Remarks</span></span>

<span data-ttu-id="f546a-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="f546a-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>