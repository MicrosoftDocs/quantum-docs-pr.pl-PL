---
uid: Microsoft.Quantum.Canon.Compose
title: Funkcja redagowania
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216765"
---
# <a name="compose-function"></a><span data-ttu-id="5393e-102">Funkcja redagowania</span><span class="sxs-lookup"><span data-stu-id="5393e-102">Compose function</span></span>

<span data-ttu-id="5393e-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5393e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5393e-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5393e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5393e-105">Zwraca składową dwóch funkcji.</span><span class="sxs-lookup"><span data-stu-id="5393e-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="5393e-106">Opis</span><span class="sxs-lookup"><span data-stu-id="5393e-106">Description</span></span>

<span data-ttu-id="5393e-107">Podaną dwie funkcje $f $ i $g $, zwracają nową funkcję reprezentującą $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="5393e-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="5393e-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5393e-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="5393e-109">zewnętrzne: "U->" V</span><span class="sxs-lookup"><span data-stu-id="5393e-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="5393e-110">Druga funkcja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5393e-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="5393e-111">wewnętrzny: brak > ' U</span><span class="sxs-lookup"><span data-stu-id="5393e-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="5393e-112">Pierwsza funkcja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5393e-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="5393e-113">Dane wyjściowe: 'R-> ' V</span><span class="sxs-lookup"><span data-stu-id="5393e-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="5393e-114">Nowa funkcja $h $, która dla wszystkich wejść $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="5393e-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5393e-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5393e-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5393e-116">'C</span><span class="sxs-lookup"><span data-stu-id="5393e-116">'T</span></span>

<span data-ttu-id="5393e-117">Typ wejścia pierwszej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5393e-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="5393e-118">' U</span><span class="sxs-lookup"><span data-stu-id="5393e-118">'U</span></span>

<span data-ttu-id="5393e-119">Typ wyjściowy pierwszej funkcji, która ma zostać zastosowana i typ wejściowy drugiej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5393e-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="5393e-120">"V</span><span class="sxs-lookup"><span data-stu-id="5393e-120">'V</span></span>

<span data-ttu-id="5393e-121">Typ wyjściowy drugiej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5393e-121">The output type of the second function to be applied.</span></span>