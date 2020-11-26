---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216391"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="13c71-102">UncurriedOpCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="13c71-102">UncurriedOpCA function</span></span>

<span data-ttu-id="13c71-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="13c71-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="13c71-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="13c71-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="13c71-105">Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.</span><span class="sxs-lookup"><span data-stu-id="13c71-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="13c71-106">Modyfikator `CA` wskazuje, że operacje są kontrolowane i sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="13c71-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="13c71-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="13c71-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="13c71-108">curriedOp: t-> ' U => [jednostką](xref:microsoft.quantum.lang-ref.unit)  jest przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="13c71-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="13c71-109">Funkcja zwracająca operacje.</span><span class="sxs-lookup"><span data-stu-id="13c71-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="13c71-110">Wynik: (t, ' U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="13c71-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="13c71-111">Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="13c71-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="13c71-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="13c71-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="13c71-113">'C</span><span class="sxs-lookup"><span data-stu-id="13c71-113">'T</span></span>

<span data-ttu-id="13c71-114">Typ pierwszego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="13c71-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="13c71-115">' U</span><span class="sxs-lookup"><span data-stu-id="13c71-115">'U</span></span>

<span data-ttu-id="13c71-116">Typ drugiego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="13c71-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="13c71-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="13c71-117">See Also</span></span>

- [<span data-ttu-id="13c71-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="13c71-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)