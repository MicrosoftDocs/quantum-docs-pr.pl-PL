---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7a1eb2afefd662f90e58798b56bc83b34ac2abfd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718821"
---
# <a name="tail-function"></a><span data-ttu-id="74d88-102">Tail — funkcja</span><span class="sxs-lookup"><span data-stu-id="74d88-102">Tail function</span></span>

<span data-ttu-id="74d88-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="74d88-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="74d88-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74d88-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74d88-105">Zwraca ostatni element tablicy.</span><span class="sxs-lookup"><span data-stu-id="74d88-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="74d88-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="74d88-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="74d88-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="74d88-107">array : 'A[]</span></span>

<span data-ttu-id="74d88-108">Tablica, do której jest pobierany ostatni element.</span><span class="sxs-lookup"><span data-stu-id="74d88-108">Array of which the last element is taken.</span></span> <span data-ttu-id="74d88-109">Tablica musi mieć długość co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="74d88-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="74d88-110">Dane wyjściowe: ' A</span><span class="sxs-lookup"><span data-stu-id="74d88-110">Output : 'A</span></span>

<span data-ttu-id="74d88-111">Ostatni element tablicy.</span><span class="sxs-lookup"><span data-stu-id="74d88-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="74d88-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="74d88-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="74d88-113">"A</span><span class="sxs-lookup"><span data-stu-id="74d88-113">'A</span></span>

<span data-ttu-id="74d88-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="74d88-114">The type of the array elements.</span></span>