---
uid: Microsoft.Quantum.Canon.Compose
title: Funkcja redagowania
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840904"
---
# <a name="compose-function"></a><span data-ttu-id="4e53f-102">Funkcja redagowania</span><span class="sxs-lookup"><span data-stu-id="4e53f-102">Compose function</span></span>

<span data-ttu-id="4e53f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e53f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e53f-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4e53f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4e53f-105">Zwraca składową dwóch funkcji.</span><span class="sxs-lookup"><span data-stu-id="4e53f-105">Returns the composition of two functions.</span></span>

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a><span data-ttu-id="4e53f-106">Opis</span><span class="sxs-lookup"><span data-stu-id="4e53f-106">Description</span></span>

<span data-ttu-id="4e53f-107">Podaną dwie funkcje $f $ i $g $, zwracają nową funkcję reprezentującą $f \circ g $.</span><span class="sxs-lookup"><span data-stu-id="4e53f-107">Given two functions $f$ and $g$, returns a new function representing $f \circ g$.</span></span>

## <a name="input"></a><span data-ttu-id="4e53f-108">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4e53f-108">Input</span></span>

### <a name="outer--u---v"></a><span data-ttu-id="4e53f-109">zewnętrzne: "U->" V</span><span class="sxs-lookup"><span data-stu-id="4e53f-109">outer : 'U -> 'V</span></span>

<span data-ttu-id="4e53f-110">Druga funkcja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4e53f-110">The second function to be applied.</span></span>


### <a name="inner--t---u"></a><span data-ttu-id="4e53f-111">wewnętrzny: brak > ' U</span><span class="sxs-lookup"><span data-stu-id="4e53f-111">inner : 'T -> 'U</span></span>

<span data-ttu-id="4e53f-112">Pierwsza funkcja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4e53f-112">The first function to be applied.</span></span>



## <a name="output--t---v"></a><span data-ttu-id="4e53f-113">Dane wyjściowe: 'R-> ' V</span><span class="sxs-lookup"><span data-stu-id="4e53f-113">Output : 'T -> 'V</span></span>

<span data-ttu-id="4e53f-114">Nowa funkcja $h $, która dla wszystkich wejść $x $, $f (g (x)) = h (x) $.</span><span class="sxs-lookup"><span data-stu-id="4e53f-114">A new function $h$ such that for all inputs $x$, $f(g(x)) = h(x)$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4e53f-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4e53f-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e53f-116">'C</span><span class="sxs-lookup"><span data-stu-id="4e53f-116">'T</span></span>

<span data-ttu-id="4e53f-117">Typ wejścia pierwszej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4e53f-117">The input type of the first function to be applied.</span></span>
### <a name="u"></a><span data-ttu-id="4e53f-118">' U</span><span class="sxs-lookup"><span data-stu-id="4e53f-118">'U</span></span>

<span data-ttu-id="4e53f-119">Typ wyjściowy pierwszej funkcji, która ma zostać zastosowana i typ wejściowy drugiej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4e53f-119">The output type of the first function to be applied and the input type of the second function to be applied.</span></span>
### <a name="v"></a><span data-ttu-id="4e53f-120">"V</span><span class="sxs-lookup"><span data-stu-id="4e53f-120">'V</span></span>

<span data-ttu-id="4e53f-121">Typ wyjściowy drugiej funkcji, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="4e53f-121">The output type of the second function to be applied.</span></span>