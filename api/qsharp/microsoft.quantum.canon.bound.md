---
uid: Microsoft.Quantum.Canon.Bound
title: Bound — funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 041f654c14f6e926d60038fee698b2b829fab8b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841064"
---
# <a name="bound-function"></a><span data-ttu-id="4fe56-102">Bound — funkcja</span><span class="sxs-lookup"><span data-stu-id="4fe56-102">Bound function</span></span>

<span data-ttu-id="4fe56-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4fe56-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4fe56-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4fe56-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4fe56-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="4fe56-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="4fe56-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4fe56-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="4fe56-107">operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="4fe56-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="4fe56-108">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="4fe56-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="4fe56-109">Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="4fe56-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4fe56-110">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="4fe56-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4fe56-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4fe56-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4fe56-112">'C</span><span class="sxs-lookup"><span data-stu-id="4fe56-112">'T</span></span>

<span data-ttu-id="4fe56-113">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="4fe56-113">The target on which each of the operations in the array act.</span></span>

## <a name="example"></a><span data-ttu-id="4fe56-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="4fe56-114">Example</span></span>

<span data-ttu-id="4fe56-115">Następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="4fe56-115">The following are equivalent:</span></span>

```qsharp
let bound = Bound([U, V]);
bound(x);
```

<span data-ttu-id="4fe56-116">oraz</span><span class="sxs-lookup"><span data-stu-id="4fe56-116">and</span></span>

```qsharp
U(x); V(x);
```

## <a name="see-also"></a><span data-ttu-id="4fe56-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4fe56-117">See Also</span></span>

- [<span data-ttu-id="4fe56-118">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="4fe56-118">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="4fe56-119">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="4fe56-119">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="4fe56-120">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="4fe56-120">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)