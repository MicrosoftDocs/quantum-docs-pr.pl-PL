---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713169"
---
# <a name="rangestart-function"></a><span data-ttu-id="b4f10-102">RangeStart, funkcja</span><span class="sxs-lookup"><span data-stu-id="b4f10-102">RangeStart function</span></span>

<span data-ttu-id="b4f10-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="b4f10-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="b4f10-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b4f10-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b4f10-105">Zwraca zdefiniowaną wartość początkową danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="b4f10-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="b4f10-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b4f10-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="b4f10-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="b4f10-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="b4f10-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b4f10-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b4f10-109">Zdefiniowana wartość początkowa danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="b4f10-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4f10-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="b4f10-110">Remarks</span></span>

<span data-ttu-id="b4f10-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="b4f10-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="b4f10-112">Należy zauważyć, że zdefiniowana wartość początkowa zakresu jest taka sama jak pierwszy element sekwencji, chyba że zakres określa pustą sekwencję (na przykład 2..</span><span class="sxs-lookup"><span data-stu-id="b4f10-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="b4f10-113">1).</span><span class="sxs-lookup"><span data-stu-id="b4f10-113">1).</span></span>