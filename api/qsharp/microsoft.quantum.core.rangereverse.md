---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213841"
---
# <a name="rangereverse-function"></a><span data-ttu-id="66800-102">RangeReverse, funkcja</span><span class="sxs-lookup"><span data-stu-id="66800-102">RangeReverse function</span></span>

<span data-ttu-id="66800-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="66800-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="66800-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="66800-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="66800-105">Zwraca nowy zakres, który jest odwrotnością zakresu wejściowego.</span><span class="sxs-lookup"><span data-stu-id="66800-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="66800-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="66800-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="66800-107">r: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="66800-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="66800-108">Zakres wejściowy.</span><span class="sxs-lookup"><span data-stu-id="66800-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="66800-109">Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="66800-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="66800-110">Nowy zakres, który jest odwrotny od danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="66800-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="66800-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="66800-111">Remarks</span></span>

<span data-ttu-id="66800-112">Należy zauważyć, że odwrócenie zakresu nie jest po prostu `end` .. `-step` .. `start` , ponieważ rzeczywisty ostatni element zakresu nie może być taki sam jak `end` .</span><span class="sxs-lookup"><span data-stu-id="66800-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>