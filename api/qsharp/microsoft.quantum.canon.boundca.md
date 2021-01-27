---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844529"
---
# <a name="boundca-function"></a><span data-ttu-id="85043-102">BoundCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="85043-102">BoundCA function</span></span>

<span data-ttu-id="85043-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="85043-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="85043-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="85043-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="85043-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="85043-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="85043-106">Modyfikator `CA` wskazuje, że wszystkie operacje w tablicy są sąsiadujące i kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="85043-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="85043-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="85043-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="85043-108">operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL []</span><span class="sxs-lookup"><span data-stu-id="85043-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="85043-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="85043-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="85043-110">Wynik: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="85043-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="85043-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="85043-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="85043-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="85043-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="85043-113">'C</span><span class="sxs-lookup"><span data-stu-id="85043-113">'T</span></span>

<span data-ttu-id="85043-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="85043-114">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="85043-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="85043-115">Example</span></span>

<span data-ttu-id="85043-116">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="85043-116">The following are equivalent:</span></span>

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

<span data-ttu-id="85043-117">oraz</span><span class="sxs-lookup"><span data-stu-id="85043-117">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="85043-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="85043-118">See Also</span></span>

- [<span data-ttu-id="85043-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="85043-119">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)