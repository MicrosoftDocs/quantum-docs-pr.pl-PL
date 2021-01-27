---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 680562228a39263ef87ba053e6b7683412947e46
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845409"
---
# <a name="tail-function"></a><span data-ttu-id="06527-102">Tail — funkcja</span><span class="sxs-lookup"><span data-stu-id="06527-102">Tail function</span></span>

<span data-ttu-id="06527-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="06527-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="06527-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="06527-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="06527-105">Zwraca ostatni element tablicy.</span><span class="sxs-lookup"><span data-stu-id="06527-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="06527-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="06527-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="06527-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="06527-107">array : 'A[]</span></span>

<span data-ttu-id="06527-108">Tablica, do której jest pobierany ostatni element.</span><span class="sxs-lookup"><span data-stu-id="06527-108">Array of which the last element is taken.</span></span> <span data-ttu-id="06527-109">Tablica musi mieć długość co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="06527-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="06527-110">Dane wyjściowe: ' A</span><span class="sxs-lookup"><span data-stu-id="06527-110">Output : 'A</span></span>

<span data-ttu-id="06527-111">Ostatni element tablicy.</span><span class="sxs-lookup"><span data-stu-id="06527-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="06527-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="06527-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="06527-113">"A</span><span class="sxs-lookup"><span data-stu-id="06527-113">'A</span></span>

<span data-ttu-id="06527-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="06527-114">The type of the array elements.</span></span>