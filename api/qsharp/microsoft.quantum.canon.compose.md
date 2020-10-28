---
uid: Microsoft.Quantum.Canon.Compose
title: Funkcja redagowania
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716492"
---
# <a name="compose-function"></a><span data-ttu-id="5923c-102">Funkcja redagowania</span><span class="sxs-lookup"><span data-stu-id="5923c-102">Compose function</span></span>

<span data-ttu-id="5923c-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5923c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5923c-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5923c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5923c-105">Zwraca składową dwóch funkcji.</span><span class="sxs-lookup"><span data-stu-id="5923c-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="5923c-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5923c-106">Description</span></span>

<span data-ttu-id="5923c-107">Podaną dwie funkcje $f $ i $g $, zwracają nową funkcję reprezentującą $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="5923c-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="5923c-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5923c-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="5923c-109">zewnętrzne: "U->" V</span><span class="sxs-lookup"><span data-stu-id="5923c-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="5923c-110">Druga funkcja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5923c-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="5923c-111">wewnętrzny: brak > ' U</span><span class="sxs-lookup"><span data-stu-id="5923c-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="5923c-112">Pierwsza funkcja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5923c-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="5923c-113">Dane wyjściowe: 'R-> ' V</span><span class="sxs-lookup"><span data-stu-id="5923c-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="5923c-114">Nowa funkcja $h $, która dla wszystkich wejść $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="5923c-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5923c-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5923c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5923c-116">'C</span><span class="sxs-lookup"><span data-stu-id="5923c-116">'T</span></span>

<span data-ttu-id="5923c-117">Typ wejścia pierwszej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5923c-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="5923c-118">' U</span><span class="sxs-lookup"><span data-stu-id="5923c-118">'U</span></span>

<span data-ttu-id="5923c-119">Typ wyjściowy pierwszej funkcji, która ma zostać zastosowana i typ wejściowy drugiej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5923c-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="5923c-120">"V</span><span class="sxs-lookup"><span data-stu-id="5923c-120">'V</span></span>

<span data-ttu-id="5923c-121">Typ wyjściowy drugiej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5923c-121">The output type of the second function to be applied.</span></span>