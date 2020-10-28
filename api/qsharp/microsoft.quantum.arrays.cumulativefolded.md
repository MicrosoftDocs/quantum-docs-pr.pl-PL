---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719397"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="73c1e-102">CumulativeFolded, funkcja</span><span class="sxs-lookup"><span data-stu-id="73c1e-102">CumulativeFolded function</span></span>

<span data-ttu-id="73c1e-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="73c1e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="73c1e-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="73c1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="73c1e-105">Łączy zamapowane i zgięcie w jedną funkcję</span><span class="sxs-lookup"><span data-stu-id="73c1e-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="73c1e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="73c1e-106">Description</span></span>

<span data-ttu-id="73c1e-107">Ta funkcja iteruje `fn` funkcję za pośrednictwem tablicy, rozpoczynając od początkowego stanu `state` i zwraca wszystkie wartości pośrednie, bez uwzględniania stanu początkowego.</span><span class="sxs-lookup"><span data-stu-id="73c1e-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="73c1e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="73c1e-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="73c1e-109">fn: ("stan, t) — stan >"</span><span class="sxs-lookup"><span data-stu-id="73c1e-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="73c1e-110">Funkcja, która ma być składana nad tablicą</span><span class="sxs-lookup"><span data-stu-id="73c1e-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="73c1e-111">stan: "stan</span><span class="sxs-lookup"><span data-stu-id="73c1e-111">state : 'State</span></span>

<span data-ttu-id="73c1e-112">Początkowy stan, który ma zostać złożony</span><span class="sxs-lookup"><span data-stu-id="73c1e-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="73c1e-113">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="73c1e-113">array : 'T[]</span></span>

<span data-ttu-id="73c1e-114">Tablica wartości, które mają zostać złożone</span><span class="sxs-lookup"><span data-stu-id="73c1e-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="73c1e-115">Dane wyjściowe: "State []</span><span class="sxs-lookup"><span data-stu-id="73c1e-115">Output : 'State[]</span></span>

<span data-ttu-id="73c1e-116">Wszystkie Stany pośrednie, w tym stan końcowy, ale nie stan początkowy.</span><span class="sxs-lookup"><span data-stu-id="73c1e-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="73c1e-117">Długość tablicy wyjściowej jest taka sama jak długość `array` .</span><span class="sxs-lookup"><span data-stu-id="73c1e-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="73c1e-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="73c1e-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="73c1e-119">"Stan</span><span class="sxs-lookup"><span data-stu-id="73c1e-119">'State</span></span>

<span data-ttu-id="73c1e-120">Typ Stanów, w których `fn` działa funkcja, tj., akceptuje jako pierwsze dane wejściowe i zwraca.</span><span class="sxs-lookup"><span data-stu-id="73c1e-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="73c1e-121">'C</span><span class="sxs-lookup"><span data-stu-id="73c1e-121">'T</span></span>

<span data-ttu-id="73c1e-122">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="73c1e-122">The type of `array` elements.</span></span>