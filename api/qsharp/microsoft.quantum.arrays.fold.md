---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkcja zgięcia
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719208"
---
# <a name="fold-function"></a><span data-ttu-id="0d57f-102">Funkcja zgięcia</span><span class="sxs-lookup"><span data-stu-id="0d57f-102">Fold function</span></span>

<span data-ttu-id="0d57f-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0d57f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0d57f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0d57f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0d57f-105">Iteruje funkcję `f` za pomocą tablicy `array` , zwracając `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="0d57f-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="0d57f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0d57f-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="0d57f-107">folder: ("State, t) — stan >"</span><span class="sxs-lookup"><span data-stu-id="0d57f-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="0d57f-108">Funkcja, która ma być składana na tablicy.</span><span class="sxs-lookup"><span data-stu-id="0d57f-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="0d57f-109">stan: "stan</span><span class="sxs-lookup"><span data-stu-id="0d57f-109">state : 'State</span></span>

<span data-ttu-id="0d57f-110">Początkowy stan folderu.</span><span class="sxs-lookup"><span data-stu-id="0d57f-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="0d57f-111">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="0d57f-111">array : 'T[]</span></span>

<span data-ttu-id="0d57f-112">Tablica wartości do przejęcia.</span><span class="sxs-lookup"><span data-stu-id="0d57f-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="0d57f-113">Wynik: "stan</span><span class="sxs-lookup"><span data-stu-id="0d57f-113">Output : 'State</span></span>

<span data-ttu-id="0d57f-114">Końcowy stan zwrócony przez folder po przeprowadzeniu iteracji dla wszystkich elementów `array` .</span><span class="sxs-lookup"><span data-stu-id="0d57f-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0d57f-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0d57f-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="0d57f-116">"Stan</span><span class="sxs-lookup"><span data-stu-id="0d57f-116">'State</span></span>

<span data-ttu-id="0d57f-117">Typ Stanów `folder` , w których działa funkcja, tj., akceptuje jako pierwszy argument i zwraca.</span><span class="sxs-lookup"><span data-stu-id="0d57f-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="0d57f-118">'C</span><span class="sxs-lookup"><span data-stu-id="0d57f-118">'T</span></span>

<span data-ttu-id="0d57f-119">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="0d57f-119">The type of `array` elements.</span></span>