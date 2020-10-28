---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716366"
---
# <a name="curriedop-function"></a><span data-ttu-id="fea09-102">CurriedOp, funkcja</span><span class="sxs-lookup"><span data-stu-id="fea09-102">CurriedOp function</span></span>

<span data-ttu-id="fea09-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="fea09-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="fea09-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fea09-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fea09-105">Zwraca wersję rozwinięte operacji dla dwóch danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="fea09-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="fea09-106">Oznacza to, że w wyniku operacji z dwoma danymi wejściowymi ta funkcja stosuje curry isomorphism $f (x, y) \equiv f (x) (y) $, aby zwrócić operację jednego danych wejściowych, która zwraca operację jednego danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="fea09-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="fea09-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="fea09-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="fea09-108">op: (t, ' U) = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="fea09-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fea09-109">Operacja, której dane wejściowe to para.</span><span class="sxs-lookup"><span data-stu-id="fea09-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="fea09-110">Wynik: brak > ' U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fea09-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="fea09-111">Operacja, która akceptuje pierwszy element pary i zwraca operację, która akceptuje jako dane wejściowe drugiego elementu danych wejściowych pierwotnej operacji.</span><span class="sxs-lookup"><span data-stu-id="fea09-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fea09-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="fea09-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fea09-113">'C</span><span class="sxs-lookup"><span data-stu-id="fea09-113">'T</span></span>

<span data-ttu-id="fea09-114">Typ pierwszego składnika funkcji zdefiniowanej w parach.</span><span class="sxs-lookup"><span data-stu-id="fea09-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="fea09-115">' U</span><span class="sxs-lookup"><span data-stu-id="fea09-115">'U</span></span>

<span data-ttu-id="fea09-116">Typ drugiego składnika funkcji zdefiniowanej w parach.</span><span class="sxs-lookup"><span data-stu-id="fea09-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="fea09-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="fea09-117">Remarks</span></span>

<span data-ttu-id="fea09-118">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="fea09-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```