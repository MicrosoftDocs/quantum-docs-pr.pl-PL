---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715213"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="abe01-102">UncurriedOpC, funkcja</span><span class="sxs-lookup"><span data-stu-id="abe01-102">UncurriedOpC function</span></span>

<span data-ttu-id="abe01-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="abe01-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="abe01-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="abe01-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="abe01-105">Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.</span><span class="sxs-lookup"><span data-stu-id="abe01-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="abe01-106">Modyfikator `C` wskazuje, że operacje są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="abe01-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="abe01-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="abe01-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="abe01-108">curriedOp: t-> ' U => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="abe01-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="abe01-109">Funkcja zwracająca operacje.</span><span class="sxs-lookup"><span data-stu-id="abe01-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="abe01-110">Dane wyjściowe: (t, ' U) => CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="abe01-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="abe01-111">Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="abe01-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="abe01-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="abe01-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="abe01-113">'C</span><span class="sxs-lookup"><span data-stu-id="abe01-113">'T</span></span>

<span data-ttu-id="abe01-114">Typ pierwszego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="abe01-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="abe01-115">' U</span><span class="sxs-lookup"><span data-stu-id="abe01-115">'U</span></span>

<span data-ttu-id="abe01-116">Typ drugiego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="abe01-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="abe01-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="abe01-117">See Also</span></span>

- [<span data-ttu-id="abe01-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="abe01-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)