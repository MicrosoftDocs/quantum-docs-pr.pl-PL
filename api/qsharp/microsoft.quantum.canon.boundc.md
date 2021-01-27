---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 6b640c0dab14778336f42098e699e7e68cc726df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841044"
---
# <a name="boundc-function"></a><span data-ttu-id="b79ea-102">BoundC, funkcja</span><span class="sxs-lookup"><span data-stu-id="b79ea-102">BoundC function</span></span>

<span data-ttu-id="b79ea-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b79ea-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b79ea-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b79ea-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b79ea-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="b79ea-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="b79ea-106">Modyfikator `C` wskazuje, że wszystkie operacje w tablicy są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="b79ea-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="b79ea-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b79ea-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="b79ea-108">operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL []</span><span class="sxs-lookup"><span data-stu-id="b79ea-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="b79ea-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="b79ea-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="b79ea-110">Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="b79ea-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b79ea-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="b79ea-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b79ea-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b79ea-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b79ea-113">'C</span><span class="sxs-lookup"><span data-stu-id="b79ea-113">'T</span></span>

<span data-ttu-id="b79ea-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="b79ea-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="b79ea-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="b79ea-115">Example</span></span>

<span data-ttu-id="b79ea-116">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="b79ea-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundC([U, V]);
bound(x);
```

<span data-ttu-id="b79ea-117">oraz</span><span class="sxs-lookup"><span data-stu-id="b79ea-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="b79ea-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b79ea-118">See Also</span></span>

- [<span data-ttu-id="b79ea-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="b79ea-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)