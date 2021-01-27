---
uid: Microsoft.Quantum.Arrays.Reversed
title: Odwrócona funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Reversed
qsharp.summary: Create an array that contains the same elements as an input array but in Reversed order.
ms.openlocfilehash: 50699465711de45ff994095e6c098550d637d608
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845457"
---
# <a name="reversed-function"></a><span data-ttu-id="79785-102">Odwrócona funkcja</span><span class="sxs-lookup"><span data-stu-id="79785-102">Reversed function</span></span>

<span data-ttu-id="79785-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="79785-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="79785-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79785-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79785-105">Utwórz tablicę zawierającą te same elementy co Tablica wejściowa, ale w odwrotnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="79785-105">Create an array that contains the same elements as an input array but in Reversed order.</span></span>

```qsharp
function Reversed<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="79785-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="79785-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="79785-107">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="79785-107">array : 'T[]</span></span>

<span data-ttu-id="79785-108">Tablica, której elementy mają być kopiowane w odwrotnej kolejności.</span><span class="sxs-lookup"><span data-stu-id="79785-108">An array whose elements are to be copied in Reversed order.</span></span>



## <a name="output--t"></a><span data-ttu-id="79785-109">Wynik: t []</span><span class="sxs-lookup"><span data-stu-id="79785-109">Output : 'T[]</span></span>

<span data-ttu-id="79785-110">Tablica zawierająca elementy `array[Length(array) - 1]` ...</span><span class="sxs-lookup"><span data-stu-id="79785-110">An array containing the elements `array[Length(array) - 1]` ..</span></span> <span data-ttu-id="79785-111">`array[0]`.</span><span class="sxs-lookup"><span data-stu-id="79785-111">`array[0]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="79785-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="79785-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79785-113">'C</span><span class="sxs-lookup"><span data-stu-id="79785-113">'T</span></span>

<span data-ttu-id="79785-114">Typ elementów tablicy.</span><span class="sxs-lookup"><span data-stu-id="79785-114">The type of the array elements.</span></span>