---
uid: Microsoft.Quantum.Arrays.Reversed
title: Odwrócona funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 99244195e581dc00db24b938f5aa1c541cd4433a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718908"
---
# <a name="reversed-function"></a><span data-ttu-id="e5584-102">Odwrócona funkcja</span><span class="sxs-lookup"><span data-stu-id="e5584-102">Reversed function</span></span>

<span data-ttu-id="e5584-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e5584-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e5584-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e5584-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e5584-105">Utwórz tablicę zawierającą te same elementy co Tablica wejściowa, ale w odwrotnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="e5584-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e5584-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e5584-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e5584-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="e5584-107">array : 'T[]</span></span>

<span data-ttu-id="e5584-108">Tablica, której elementy mają być kopiowane w odwrotnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="e5584-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="e5584-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="e5584-109">Output : 'T[]</span></span>

<span data-ttu-id="e5584-110">Tablica zawierająca elementy `array[Length(array) - 1]` ...</span><span class="sxs-lookup"><span data-stu-id="e5584-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="e5584-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="e5584-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e5584-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e5584-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5584-113">'C</span><span class="sxs-lookup"><span data-stu-id="e5584-113">'T</span></span>

<span data-ttu-id="e5584-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="e5584-114">The type of the array elements.</span></span>