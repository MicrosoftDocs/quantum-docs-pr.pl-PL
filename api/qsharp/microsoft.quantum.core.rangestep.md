---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213807"
---
# <a name="rangestep-function"></a><span data-ttu-id="075cc-102">RangeStep, funkcja</span><span class="sxs-lookup"><span data-stu-id="075cc-102">RangeStep function</span></span>

<span data-ttu-id="075cc-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="075cc-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="075cc-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="075cc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="075cc-105">Zwraca liczbę całkowitą określającą sposób obliczania następnej wartości zakresu.</span><span class="sxs-lookup"><span data-stu-id="075cc-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="075cc-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="075cc-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="075cc-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="075cc-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="075cc-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="075cc-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="075cc-109">Zdefiniowana wartość kroku danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="075cc-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="075cc-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="075cc-110">Remarks</span></span>

<span data-ttu-id="075cc-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="075cc-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>