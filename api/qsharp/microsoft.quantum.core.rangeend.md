---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224041"
---
# <a name="rangeend-function"></a><span data-ttu-id="986f1-102">RangeEnd, funkcja</span><span class="sxs-lookup"><span data-stu-id="986f1-102">RangeEnd function</span></span>

<span data-ttu-id="986f1-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="986f1-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="986f1-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="986f1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="986f1-105">Zwraca zdefiniowaną wartość końcową danego zakresu, która nie musi być ostatnim elementem w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="986f1-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="986f1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="986f1-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="986f1-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="986f1-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="986f1-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="986f1-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="986f1-109">Zdefiniowana wartość końcowa danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="986f1-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="986f1-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="986f1-110">Remarks</span></span>

<span data-ttu-id="986f1-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="986f1-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="986f1-112">Należy zauważyć, że zdefiniowana wartość końcowa zakresu może różnić się od ostatniego elementu w sekwencji określonej przez zakres; na przykład, w zakresie 0..</span><span class="sxs-lookup"><span data-stu-id="986f1-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="986f1-113">2..</span><span class="sxs-lookup"><span data-stu-id="986f1-113">2 ..</span></span> <span data-ttu-id="986f1-114">5 ostatni element to 4, ale wartość końcowa to 5.</span><span class="sxs-lookup"><span data-stu-id="986f1-114">5 the last element is 4 but the end value is 5.</span></span>