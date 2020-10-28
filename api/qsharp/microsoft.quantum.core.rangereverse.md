---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713230"
---
# <a name="rangereverse-function"></a><span data-ttu-id="835ba-102">RangeReverse, funkcja</span><span class="sxs-lookup"><span data-stu-id="835ba-102">RangeReverse function</span></span>

<span data-ttu-id="835ba-103">Przestrzeń nazw: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="835ba-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="835ba-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="835ba-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="835ba-105">Zwraca nowy zakres, który jest odwrotnością zakresu wejściowego.</span><span class="sxs-lookup"><span data-stu-id="835ba-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="835ba-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="835ba-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="835ba-107">r: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="835ba-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="835ba-108">Zakres wejściowy.</span><span class="sxs-lookup"><span data-stu-id="835ba-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="835ba-109">Dane wyjściowe: [zakres](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="835ba-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="835ba-110">Nowy zakres, który jest odwrotny od danego zakresu.</span><span class="sxs-lookup"><span data-stu-id="835ba-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="835ba-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="835ba-111">Remarks</span></span>

<span data-ttu-id="835ba-112">Należy zauważyć, że odwrócenie zakresu nie jest po prostu `end` .. `-step` .. `start` , ponieważ rzeczywisty ostatni element zakresu nie może być taki sam jak `end` .</span><span class="sxs-lookup"><span data-stu-id="835ba-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>