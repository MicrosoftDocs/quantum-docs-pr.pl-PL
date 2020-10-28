---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713244"
---
# <a name="rangeend-function"></a><span data-ttu-id="9e0d2-102">RangeEnd, funkcja</span><span class="sxs-lookup"><span data-stu-id="9e0d2-102">RangeEnd function</span></span>

<span data-ttu-id="9e0d2-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="9e0d2-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="9e0d2-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e0d2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e0d2-105">Zwraca zdefiniowaną wartość końcową danego zakresu, która nie musi być ostatnim elementem w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="9e0d2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9e0d2-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="9e0d2-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="9e0d2-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="9e0d2-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e0d2-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e0d2-109">Zdefiniowana wartość końcowa danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="9e0d2-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="9e0d2-110">Remarks</span></span>

<span data-ttu-id="9e0d2-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="9e0d2-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="9e0d2-112">Należy zauważyć, że zdefiniowana wartość końcowa zakresu może różnić się od ostatniego elementu w sekwencji określonej przez zakres; na przykład, w zakresie 0..</span><span class="sxs-lookup"><span data-stu-id="9e0d2-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="9e0d2-113">2..</span><span class="sxs-lookup"><span data-stu-id="9e0d2-113">2 ..</span></span> <span data-ttu-id="9e0d2-114">5 ostatni element to 4, ale wartość końcowa to 5.</span><span class="sxs-lookup"><span data-stu-id="9e0d2-114">5 the last element is 4 but the end value is 5.</span></span>