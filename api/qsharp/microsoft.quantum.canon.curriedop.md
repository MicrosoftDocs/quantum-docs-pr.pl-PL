---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 6c1917d6f1ee69cb29fed1ab173106af1e206533
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216629"
---
# <a name="curriedop-function"></a><span data-ttu-id="16249-102">CurriedOp, funkcja</span><span class="sxs-lookup"><span data-stu-id="16249-102">CurriedOp function</span></span>

<span data-ttu-id="16249-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="16249-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="16249-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16249-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16249-105">Zwraca wersję rozwinięte operacji dla dwóch danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="16249-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="16249-106">Oznacza to, że w wyniku operacji z dwoma danymi wejściowymi ta funkcja stosuje curry isomorphism $f (x, y) \equiv f (x) (y) $, aby zwrócić operację jednego danych wejściowych, która zwraca operację jednego danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="16249-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="16249-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="16249-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="16249-108">op: (t, ' U) = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="16249-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="16249-109">Operacja, której dane wejściowe to para.</span><span class="sxs-lookup"><span data-stu-id="16249-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="16249-110">Wynik: brak > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16249-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="16249-111">Operacja, która akceptuje pierwszy element pary i zwraca operację, która akceptuje jako dane wejściowe drugiego elementu danych wejściowych pierwotnej operacji.</span><span class="sxs-lookup"><span data-stu-id="16249-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="16249-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="16249-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16249-113">'C</span><span class="sxs-lookup"><span data-stu-id="16249-113">'T</span></span>

<span data-ttu-id="16249-114">Typ pierwszego składnika funkcji zdefiniowanej w parach.</span><span class="sxs-lookup"><span data-stu-id="16249-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="16249-115">' U</span><span class="sxs-lookup"><span data-stu-id="16249-115">'U</span></span>

<span data-ttu-id="16249-116">Typ drugiego składnika funkcji zdefiniowanej w parach.</span><span class="sxs-lookup"><span data-stu-id="16249-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="16249-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="16249-117">Remarks</span></span>

<span data-ttu-id="16249-118">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="16249-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```