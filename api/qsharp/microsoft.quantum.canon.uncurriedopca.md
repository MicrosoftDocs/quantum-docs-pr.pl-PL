---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715204"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="df0ce-102">UncurriedOpCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="df0ce-102">UncurriedOpCA function</span></span>

<span data-ttu-id="df0ce-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="df0ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="df0ce-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df0ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df0ce-105">Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.</span><span class="sxs-lookup"><span data-stu-id="df0ce-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="df0ce-106">Modyfikator `CA` wskazuje, że operacje są kontrolowane i sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="df0ce-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="df0ce-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="df0ce-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="df0ce-108">curriedOp: t-> ' U => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik</span><span class="sxs-lookup"><span data-stu-id="df0ce-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="df0ce-109">Funkcja zwracająca operacje.</span><span class="sxs-lookup"><span data-stu-id="df0ce-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="df0ce-110">Dane wyjściowe: (t, ' U) => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL + przymiotnik</span><span class="sxs-lookup"><span data-stu-id="df0ce-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="df0ce-111">Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="df0ce-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="df0ce-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="df0ce-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="df0ce-113">'C</span><span class="sxs-lookup"><span data-stu-id="df0ce-113">'T</span></span>

<span data-ttu-id="df0ce-114">Typ pierwszego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="df0ce-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="df0ce-115">' U</span><span class="sxs-lookup"><span data-stu-id="df0ce-115">'U</span></span>

<span data-ttu-id="df0ce-116">Typ drugiego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="df0ce-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="df0ce-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="df0ce-117">See Also</span></span>

- [<span data-ttu-id="df0ce-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="df0ce-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)