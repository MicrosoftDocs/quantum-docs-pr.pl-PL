---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831361"
---
# <a name="rangeend-function"></a><span data-ttu-id="18d97-102">RangeEnd, funkcja</span><span class="sxs-lookup"><span data-stu-id="18d97-102">RangeEnd function</span></span>

<span data-ttu-id="18d97-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="18d97-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="18d97-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="18d97-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="18d97-105">Zwraca zdefiniowaną wartość końcową danego zakresu, która nie musi być ostatnim elementem w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="18d97-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="18d97-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="18d97-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="18d97-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="18d97-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="18d97-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="18d97-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="18d97-109">Zdefiniowana wartość końcowa danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="18d97-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="18d97-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="18d97-110">Remarks</span></span>

<span data-ttu-id="18d97-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="18d97-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="18d97-112">Należy zauważyć, że zdefiniowana wartość końcowa zakresu może różnić się od ostatniego elementu w sekwencji określonej przez zakres; na przykład, w zakresie 0..</span><span class="sxs-lookup"><span data-stu-id="18d97-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="18d97-113">2..</span><span class="sxs-lookup"><span data-stu-id="18d97-113">2 ..</span></span> <span data-ttu-id="18d97-114">5 ostatni element to 4, ale wartość końcowa to 5.</span><span class="sxs-lookup"><span data-stu-id="18d97-114">5 the last element is 4 but the end value is 5.</span></span>