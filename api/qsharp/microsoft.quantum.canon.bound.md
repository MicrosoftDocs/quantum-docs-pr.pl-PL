---
uid: Microsoft.Quantum.Canon.Bound
title: Bound — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: 34ca2b79d0ee09bd3b5b5b3f0c0b20420d5b3882
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716702"
---
# <a name="bound-function"></a><span data-ttu-id="7787f-102">Bound — funkcja</span><span class="sxs-lookup"><span data-stu-id="7787f-102">Bound function</span></span>

<span data-ttu-id="7787f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7787f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7787f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7787f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7787f-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="7787f-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="7787f-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="7787f-106">Input</span></span>

### <a name="operations--t--unit-"></a><span data-ttu-id="7787f-107">operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)> []</span><span class="sxs-lookup"><span data-stu-id="7787f-107">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="7787f-108">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="7787f-108">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="7787f-109">Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="7787f-109">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7787f-110">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="7787f-110">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7787f-111">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="7787f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7787f-112">'C</span><span class="sxs-lookup"><span data-stu-id="7787f-112">'T</span></span>

<span data-ttu-id="7787f-113">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="7787f-113">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="7787f-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="7787f-114">See Also</span></span>

- [<span data-ttu-id="7787f-115">Microsoft. Quantum. Canon. BoundC</span><span class="sxs-lookup"><span data-stu-id="7787f-115">Microsoft.Quantum.Canon.BoundC</span></span>](xref:Microsoft.Quantum.Canon.BoundC)
- [<span data-ttu-id="7787f-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="7787f-116">Microsoft.Quantum.Canon.BoundA</span></span>](xref:Microsoft.Quantum.Canon.BoundA)
- [<span data-ttu-id="7787f-117">Microsoft. Quantum. Canon. BoundCA</span><span class="sxs-lookup"><span data-stu-id="7787f-117">Microsoft.Quantum.Canon.BoundCA</span></span>](xref:Microsoft.Quantum.Canon.BoundCA)