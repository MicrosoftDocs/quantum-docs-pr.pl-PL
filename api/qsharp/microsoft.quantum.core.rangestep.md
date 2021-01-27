---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853599"
---
# <a name="rangestep-function"></a><span data-ttu-id="05f9f-102">RangeStep, funkcja</span><span class="sxs-lookup"><span data-stu-id="05f9f-102">RangeStep function</span></span>

<span data-ttu-id="05f9f-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="05f9f-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="05f9f-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="05f9f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="05f9f-105">Zwraca liczbę całkowitą określającą sposób obliczania następnej wartości zakresu.</span><span class="sxs-lookup"><span data-stu-id="05f9f-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="05f9f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="05f9f-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="05f9f-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="05f9f-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="05f9f-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="05f9f-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="05f9f-109">Zdefiniowana wartość kroku danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="05f9f-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="05f9f-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="05f9f-110">Remarks</span></span>

<span data-ttu-id="05f9f-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="05f9f-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>