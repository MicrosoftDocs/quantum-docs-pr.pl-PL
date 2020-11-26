---
uid: Microsoft.Quantum.Arrays.Reversed
title: Odwrócona funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 270f15c1d10b4397e258c750876095efc2b8e951
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220437"
---
# <a name="reversed-function"></a><span data-ttu-id="104d5-102">Odwrócona funkcja</span><span class="sxs-lookup"><span data-stu-id="104d5-102">Reversed function</span></span>

<span data-ttu-id="104d5-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="104d5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="104d5-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="104d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="104d5-105">Utwórz tablicę zawierającą te same elementy co Tablica wejściowa, ale w odwrotnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="104d5-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="104d5-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="104d5-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="104d5-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="104d5-107">array : 'T[]</span></span>

<span data-ttu-id="104d5-108">Tablica, której elementy mają być kopiowane w odwrotnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="104d5-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="104d5-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="104d5-109">Output : 'T[]</span></span>

<span data-ttu-id="104d5-110">Tablica zawierająca elementy `array[Length(array) - 1]` ...</span><span class="sxs-lookup"><span data-stu-id="104d5-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="104d5-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="104d5-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="104d5-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="104d5-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="104d5-113">'C</span><span class="sxs-lookup"><span data-stu-id="104d5-113">'T</span></span>

<span data-ttu-id="104d5-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="104d5-114">The type of the array elements.</span></span>