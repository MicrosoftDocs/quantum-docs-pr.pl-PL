---
uid: Microsoft.Quantum.Arrays.Fold
title: Funkcja zgięcia
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848605"
---
# <a name="fold-function"></a><span data-ttu-id="448d9-102">Funkcja zgięcia</span><span class="sxs-lookup"><span data-stu-id="448d9-102">Fold function</span></span>

<span data-ttu-id="448d9-103">Przestrzeń nazw: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="448d9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="448d9-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="448d9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="448d9-105">Iteruje funkcję `f` za pomocą tablicy `array` , zwracając `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="448d9-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="448d9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="448d9-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="448d9-107">folder: ("State, t) — stan >"</span><span class="sxs-lookup"><span data-stu-id="448d9-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="448d9-108">Funkcja, która ma być składana na tablicy.</span><span class="sxs-lookup"><span data-stu-id="448d9-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="448d9-109">stan: "stan</span><span class="sxs-lookup"><span data-stu-id="448d9-109">state : 'State</span></span>

<span data-ttu-id="448d9-110">Początkowy stan folderu.</span><span class="sxs-lookup"><span data-stu-id="448d9-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="448d9-111">Tablica: t []</span><span class="sxs-lookup"><span data-stu-id="448d9-111">array : 'T[]</span></span>

<span data-ttu-id="448d9-112">Tablica wartości do przejęcia.</span><span class="sxs-lookup"><span data-stu-id="448d9-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="448d9-113">Wynik: "stan</span><span class="sxs-lookup"><span data-stu-id="448d9-113">Output : 'State</span></span>

<span data-ttu-id="448d9-114">Końcowy stan zwrócony przez folder po przeprowadzeniu iteracji dla wszystkich elementów `array` .</span><span class="sxs-lookup"><span data-stu-id="448d9-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="448d9-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="448d9-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="448d9-116">"Stan</span><span class="sxs-lookup"><span data-stu-id="448d9-116">'State</span></span>

<span data-ttu-id="448d9-117">Typ Stanów `folder` , w których działa funkcja, tj., akceptuje jako pierwszy argument i zwraca.</span><span class="sxs-lookup"><span data-stu-id="448d9-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="448d9-118">'C</span><span class="sxs-lookup"><span data-stu-id="448d9-118">'T</span></span>

<span data-ttu-id="448d9-119">Typ `array` elementów.</span><span class="sxs-lookup"><span data-stu-id="448d9-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="448d9-120">Przykład</span><span class="sxs-lookup"><span data-stu-id="448d9-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```