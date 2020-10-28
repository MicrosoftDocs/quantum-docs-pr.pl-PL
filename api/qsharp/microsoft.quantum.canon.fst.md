---
uid: Microsoft.Quantum.Canon.Fst
title: FST —, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 88ff5e29de9eeefcc1e207f277c37c63cb0faade
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716184"
---
# <a name="fst-function"></a><span data-ttu-id="b871d-102">FST —, funkcja</span><span class="sxs-lookup"><span data-stu-id="b871d-102">Fst function</span></span>

<span data-ttu-id="b871d-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b871d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b871d-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b871d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b871d-105">Dana para zwraca swój pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="b871d-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="b871d-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b871d-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="b871d-107">para: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="b871d-107">pair : ('T,'U)</span></span>

<span data-ttu-id="b871d-108">Krotka z dwoma elementami.</span><span class="sxs-lookup"><span data-stu-id="b871d-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b871d-109">Dane wyjściowe: 'T</span><span class="sxs-lookup"><span data-stu-id="b871d-109">Output : 'T</span></span>

<span data-ttu-id="b871d-110">Pierwszy element `pair` .</span><span class="sxs-lookup"><span data-stu-id="b871d-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b871d-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b871d-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b871d-112">'C</span><span class="sxs-lookup"><span data-stu-id="b871d-112">'T</span></span>

<span data-ttu-id="b871d-113">Typ pierwszego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="b871d-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="b871d-114">' U</span><span class="sxs-lookup"><span data-stu-id="b871d-114">'U</span></span>

<span data-ttu-id="b871d-115">Typ drugiego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="b871d-115">The type of the pair's second member.</span></span>