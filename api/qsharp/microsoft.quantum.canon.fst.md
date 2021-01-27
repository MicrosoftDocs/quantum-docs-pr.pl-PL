---
uid: Microsoft.Quantum.Canon.Fst
title: FST —, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840517"
---
# <a name="fst-function"></a><span data-ttu-id="28ca2-102">FST —, funkcja</span><span class="sxs-lookup"><span data-stu-id="28ca2-102">Fst function</span></span>

<span data-ttu-id="28ca2-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="28ca2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="28ca2-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28ca2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28ca2-105">Dana para zwraca swój pierwszy element.</span><span class="sxs-lookup"><span data-stu-id="28ca2-105">Given a pair, returns its first element.</span></span>

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a><span data-ttu-id="28ca2-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="28ca2-106">Input</span></span>

### <a name="pair--tu"></a><span data-ttu-id="28ca2-107">para: ('T, ' U)</span><span class="sxs-lookup"><span data-stu-id="28ca2-107">pair : ('T,'U)</span></span>

<span data-ttu-id="28ca2-108">Krotka z dwoma elementami.</span><span class="sxs-lookup"><span data-stu-id="28ca2-108">A tuple with two elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="28ca2-109">Dane wyjściowe: 'T</span><span class="sxs-lookup"><span data-stu-id="28ca2-109">Output : 'T</span></span>

<span data-ttu-id="28ca2-110">Pierwszy element `pair` .</span><span class="sxs-lookup"><span data-stu-id="28ca2-110">The first element of `pair`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="28ca2-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="28ca2-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="28ca2-112">'C</span><span class="sxs-lookup"><span data-stu-id="28ca2-112">'T</span></span>

<span data-ttu-id="28ca2-113">Typ pierwszego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="28ca2-113">The type of the pair's first member.</span></span>
### <a name="u"></a><span data-ttu-id="28ca2-114">' U</span><span class="sxs-lookup"><span data-stu-id="28ca2-114">'U</span></span>

<span data-ttu-id="28ca2-115">Typ drugiego elementu członkowskiego pary.</span><span class="sxs-lookup"><span data-stu-id="28ca2-115">The type of the pair's second member.</span></span>