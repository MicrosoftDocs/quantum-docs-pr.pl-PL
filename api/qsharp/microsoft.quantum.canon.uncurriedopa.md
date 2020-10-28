---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: 21df20354ad2388891f32b1bf1c7781287904983
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715218"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="a8bfd-102">UncurriedOpA, funkcja</span><span class="sxs-lookup"><span data-stu-id="a8bfd-102">UncurriedOpA function</span></span>

<span data-ttu-id="a8bfd-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a8bfd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a8bfd-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a8bfd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a8bfd-105">Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.</span><span class="sxs-lookup"><span data-stu-id="a8bfd-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="a8bfd-106">Modyfikator `A` wskazuje, że operacje są sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="a8bfd-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="a8bfd-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="a8bfd-107">Input</span></span>

### <a name="curriedop--t---u--unit-adj"></a><span data-ttu-id="a8bfd-108">curriedOp: > ' U => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8bfd-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a8bfd-109">Funkcja zwracająca operacje.</span><span class="sxs-lookup"><span data-stu-id="a8bfd-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-adj"></a><span data-ttu-id="a8bfd-110">Wynik: (t, ' U) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a8bfd-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="a8bfd-111">Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="a8bfd-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a8bfd-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="a8bfd-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a8bfd-113">'C</span><span class="sxs-lookup"><span data-stu-id="a8bfd-113">'T</span></span>

<span data-ttu-id="a8bfd-114">Typ pierwszego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="a8bfd-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="a8bfd-115">' U</span><span class="sxs-lookup"><span data-stu-id="a8bfd-115">'U</span></span>

<span data-ttu-id="a8bfd-116">Typ drugiego argumentu funkcji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="a8bfd-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8bfd-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a8bfd-117">See Also</span></span>

- [<span data-ttu-id="a8bfd-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="a8bfd-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)