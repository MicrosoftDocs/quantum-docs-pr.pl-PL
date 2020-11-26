---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204593"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="70620-102">UncurriedOpC, funkcja</span><span class="sxs-lookup"><span data-stu-id="70620-102">UncurriedOpC function</span></span>

<span data-ttu-id="70620-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="70620-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="70620-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="70620-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="70620-105">Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.</span><span class="sxs-lookup"><span data-stu-id="70620-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="70620-106">Modyfikator `C` wskazuje, że operacje są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="70620-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="70620-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="70620-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="70620-108">curriedOp: > ' U => [jednostką](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="70620-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="70620-109">Funkcja zwracająca operacje.</span><span class="sxs-lookup"><span data-stu-id="70620-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="70620-110">Wynik: (t, ' U) = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="70620-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="70620-111">Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="70620-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="70620-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="70620-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="70620-113">'C</span><span class="sxs-lookup"><span data-stu-id="70620-113">'T</span></span>

<span data-ttu-id="70620-114">Typ pierwszego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="70620-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="70620-115">' U</span><span class="sxs-lookup"><span data-stu-id="70620-115">'U</span></span>

<span data-ttu-id="70620-116">Typ drugiego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="70620-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="70620-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="70620-117">See Also</span></span>

- [<span data-ttu-id="70620-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="70620-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)