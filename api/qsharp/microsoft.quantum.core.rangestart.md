---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831115"
---
# <a name="rangestart-function"></a><span data-ttu-id="3f801-102">RangeStart, funkcja</span><span class="sxs-lookup"><span data-stu-id="3f801-102">RangeStart function</span></span>

<span data-ttu-id="3f801-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="3f801-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="3f801-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3f801-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3f801-105">Zwraca zdefiniowaną wartość początkową danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="3f801-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="3f801-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3f801-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="3f801-107">zakres: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="3f801-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="3f801-108">Wynik: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3f801-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3f801-109">Zdefiniowana wartość początkowa danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="3f801-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f801-110">Uwagi</span><span class="sxs-lookup"><span data-stu-id="3f801-110">Remarks</span></span>

<span data-ttu-id="3f801-111">Pierwszy element wyrażenia zakresu to `start` , jego drugi element jest, `start+step` trzeci element jest `start+step+step` itd., do do `end` .</span><span class="sxs-lookup"><span data-stu-id="3f801-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="3f801-112">Należy zauważyć, że zdefiniowana wartość początkowa zakresu jest taka sama jak pierwszy element sekwencji, chyba że zakres określa pustą sekwencję (na przykład 2..</span><span class="sxs-lookup"><span data-stu-id="3f801-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="3f801-113">1).</span><span class="sxs-lookup"><span data-stu-id="3f801-113">1).</span></span>