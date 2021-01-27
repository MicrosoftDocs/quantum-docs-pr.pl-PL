---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853662"
---
# <a name="rangereverse-function"></a><span data-ttu-id="ce554-102">RangeReverse, funkcja</span><span class="sxs-lookup"><span data-stu-id="ce554-102">RangeReverse function</span></span>

<span data-ttu-id="ce554-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="ce554-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="ce554-104">Pakiet: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ce554-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ce554-105">Zwraca nowy zakres, który jest odwrotnością zakresu wejściowego.</span><span class="sxs-lookup"><span data-stu-id="ce554-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="ce554-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="ce554-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="ce554-107">r: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ce554-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ce554-108">Zakres wejściowy.</span><span class="sxs-lookup"><span data-stu-id="ce554-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="ce554-109">Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="ce554-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="ce554-110">Nowy zakres, który jest odwrotny od danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="ce554-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="ce554-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="ce554-111">Remarks</span></span>

<span data-ttu-id="ce554-112">Należy zauważyć, że odwrócenie zakresu nie jest po prostu `end` .. `-step` .. `start` , ponieważ rzeczywisty ostatni element zakresu nie może być taki sam jak `end` .</span><span class="sxs-lookup"><span data-stu-id="ce554-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>