---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715241"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="3df50-102">UncurriedOp, funkcja</span><span class="sxs-lookup"><span data-stu-id="3df50-102">UncurriedOp function</span></span>

<span data-ttu-id="3df50-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3df50-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3df50-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3df50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3df50-105">Dana funkcja, która zwraca operacje, zwraca nową operację, która pobiera dane wejściowe jako krotki.</span><span class="sxs-lookup"><span data-stu-id="3df50-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="3df50-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3df50-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="3df50-107">curriedOp: t-> ' U = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3df50-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3df50-108">Funkcja zwracająca operacje.</span><span class="sxs-lookup"><span data-stu-id="3df50-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="3df50-109">Wynik: (t, ' U) = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3df50-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3df50-110">Nowa operacja `op` , która `op(t, u)` jest równoważna z `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="3df50-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3df50-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3df50-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3df50-112">'C</span><span class="sxs-lookup"><span data-stu-id="3df50-112">'T</span></span>

<span data-ttu-id="3df50-113">Typ pierwszego wejścia do operacji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="3df50-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="3df50-114">' U</span><span class="sxs-lookup"><span data-stu-id="3df50-114">'U</span></span>

<span data-ttu-id="3df50-115">Typ drugiego danych wejściowych do operacji rozwinięte.</span><span class="sxs-lookup"><span data-stu-id="3df50-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="3df50-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3df50-116">See Also</span></span>

- [<span data-ttu-id="3df50-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="3df50-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="3df50-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="3df50-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="3df50-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="3df50-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)