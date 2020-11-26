---
uid: Microsoft.Quantum.Canon.Fst
title: FST —, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206939"
---
# <a name="fst-function"></a><span data-ttu-id="4683a-102">FST —, funkcja</span><span class="sxs-lookup"><span data-stu-id="4683a-102">Fst function</span></span>

<span data-ttu-id="4683a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4683a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4683a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4683a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4683a-105">Dana para zwraca swój pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="4683a-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="4683a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4683a-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="4683a-107">para: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="4683a-107">pair : ('T,'U)</span></span>

<span data-ttu-id="4683a-108">Krotka z dwoma elementami.</span><span class="sxs-lookup"><span data-stu-id="4683a-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="4683a-109">Dane wyjściowe: 'T</span><span class="sxs-lookup"><span data-stu-id="4683a-109">Output : 'T</span></span>

<span data-ttu-id="4683a-110">Pierwszy element `pair` .</span><span class="sxs-lookup"><span data-stu-id="4683a-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4683a-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4683a-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4683a-112">'C</span><span class="sxs-lookup"><span data-stu-id="4683a-112">'T</span></span>

<span data-ttu-id="4683a-113">Typ pierwszego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="4683a-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="4683a-114">' U</span><span class="sxs-lookup"><span data-stu-id="4683a-114">'U</span></span>

<span data-ttu-id="4683a-115">Typ drugiego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="4683a-115">The type of the pair's second member.</span></span>