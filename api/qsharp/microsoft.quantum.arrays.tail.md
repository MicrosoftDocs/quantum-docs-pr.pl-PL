---
uid: Microsoft.Quantum.Arrays.Tail
title: Tail — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Tail
qsharp.summary: Returns the last element of the array.
ms.openlocfilehash: 7084cd8bc75f295024dce361153b58490074cdc5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220097"
---
# <a name="tail-function"></a><span data-ttu-id="9f158-102">Tail — funkcja</span><span class="sxs-lookup"><span data-stu-id="9f158-102">Tail function</span></span>

<span data-ttu-id="9f158-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9f158-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9f158-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9f158-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9f158-105">Zwraca ostatni element tablicy.</span><span class="sxs-lookup"><span data-stu-id="9f158-105">Returns the last element of the array.</span></span>

```qsharp
function Tail<'A> (array : 'A[]) : 'A
```


## <a name="input"></a><span data-ttu-id="9f158-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="9f158-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9f158-107">Tablica: "A []</span><span class="sxs-lookup"><span data-stu-id="9f158-107">array : 'A[]</span></span>

<span data-ttu-id="9f158-108">Tablica, do której jest pobierany ostatni element.</span><span class="sxs-lookup"><span data-stu-id="9f158-108">Array of which the last element is taken.</span></span> <span data-ttu-id="9f158-109">Tablica musi mieć długość co najmniej 1.</span><span class="sxs-lookup"><span data-stu-id="9f158-109">Array must have length at least 1.</span></span>



## <a name="output--a"></a><span data-ttu-id="9f158-110">Dane wyjściowe: ' A</span><span class="sxs-lookup"><span data-stu-id="9f158-110">Output : 'A</span></span>

<span data-ttu-id="9f158-111">Ostatni element tablicy.</span><span class="sxs-lookup"><span data-stu-id="9f158-111">The last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9f158-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="9f158-112">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9f158-113">"A</span><span class="sxs-lookup"><span data-stu-id="9f158-113">'A</span></span>

<span data-ttu-id="9f158-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="9f158-114">The type of the array elements.</span></span>