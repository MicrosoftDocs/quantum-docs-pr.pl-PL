---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204627"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="769fe-102">UncurriedOpA, funkcja</span><span class="sxs-lookup"><span data-stu-id="769fe-102">UncurriedOpA function</span></span>

<span data-ttu-id="769fe-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="769fe-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="769fe-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="769fe-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="769fe-105">Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.</span><span class="sxs-lookup"><span data-stu-id="769fe-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="769fe-106">Modyfikator `A` wskazuje, że operacje są sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="769fe-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="769fe-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="769fe-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="769fe-108">curriedOp: > ' U => [jednostką](xref:microsoft.quantum.lang-ref.unit)  jest przymiotnik</span><span class="sxs-lookup"><span data-stu-id="769fe-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="769fe-109">Funkcja zwracająca operacje.</span><span class="sxs-lookup"><span data-stu-id="769fe-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="769fe-110">Wynik: (t, ' U) => [Jednostka](xref:microsoft.quantum.lang-ref.unit)  jest korektą</span><span class="sxs-lookup"><span data-stu-id="769fe-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="769fe-111">Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="769fe-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="769fe-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="769fe-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="769fe-113">'C</span><span class="sxs-lookup"><span data-stu-id="769fe-113">'T</span></span>

<span data-ttu-id="769fe-114">Typ pierwszego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="769fe-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="769fe-115">' U</span><span class="sxs-lookup"><span data-stu-id="769fe-115">'U</span></span>

<span data-ttu-id="769fe-116">Typ drugiego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="769fe-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="769fe-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="769fe-117">See Also</span></span>

- [<span data-ttu-id="769fe-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="769fe-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)