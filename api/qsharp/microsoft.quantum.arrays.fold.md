---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkcja zgięcia
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221168"
---
# <a name="fold-function"></a><span data-ttu-id="e7c1e-102">Funkcja zgięcia</span><span class="sxs-lookup"><span data-stu-id="e7c1e-102">Fold function</span></span>

<span data-ttu-id="e7c1e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e7c1e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e7c1e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7c1e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7c1e-105">Iteruje funkcję `f` za pomocą tablicy `array` , zwracając `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="e7c1e-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="e7c1e-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="e7c1e-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="e7c1e-107">folder: ("State, t) — stan >"</span><span class="sxs-lookup"><span data-stu-id="e7c1e-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="e7c1e-108">Funkcja, która ma być składana na tablicy.</span><span class="sxs-lookup"><span data-stu-id="e7c1e-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="e7c1e-109">stan: "stan</span><span class="sxs-lookup"><span data-stu-id="e7c1e-109">state : 'State</span></span>

<span data-ttu-id="e7c1e-110">Początkowy stan folderu.</span><span class="sxs-lookup"><span data-stu-id="e7c1e-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="e7c1e-111">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="e7c1e-111">array : 'T[]</span></span>

<span data-ttu-id="e7c1e-112">Tablica wartości do przejęcia.</span><span class="sxs-lookup"><span data-stu-id="e7c1e-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="e7c1e-113">Wynik: "stan</span><span class="sxs-lookup"><span data-stu-id="e7c1e-113">Output : 'State</span></span>

<span data-ttu-id="e7c1e-114">Końcowy stan zwrócony przez folder po przeprowadzeniu iteracji dla wszystkich elementów `array` .</span><span class="sxs-lookup"><span data-stu-id="e7c1e-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e7c1e-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="e7c1e-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="e7c1e-116">"Stan</span><span class="sxs-lookup"><span data-stu-id="e7c1e-116">'State</span></span>

<span data-ttu-id="e7c1e-117">Typ Stanów `folder` , w których działa funkcja, tj., akceptuje jako pierwszy argument i zwraca.</span><span class="sxs-lookup"><span data-stu-id="e7c1e-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="e7c1e-118">'C</span><span class="sxs-lookup"><span data-stu-id="e7c1e-118">'T</span></span>

<span data-ttu-id="e7c1e-119">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="e7c1e-119">The type of `array` elements.</span></span>