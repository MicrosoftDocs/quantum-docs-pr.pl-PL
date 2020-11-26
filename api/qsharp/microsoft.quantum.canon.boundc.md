---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207585"
---
# <a name="boundc-function"></a><span data-ttu-id="156d7-102">BoundC, funkcja</span><span class="sxs-lookup"><span data-stu-id="156d7-102">BoundC function</span></span>

<span data-ttu-id="156d7-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="156d7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="156d7-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="156d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="156d7-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="156d7-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="156d7-106">Modyfikator `C` wskazuje, że wszystkie operacje w tablicy są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="156d7-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="156d7-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="156d7-107">Input</span></span>

### <a name="operations--t--unit--is-ctl"></a><span data-ttu-id="156d7-108">operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL []</span><span class="sxs-lookup"><span data-stu-id="156d7-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="156d7-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="156d7-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="156d7-110">Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="156d7-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="156d7-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="156d7-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="156d7-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="156d7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="156d7-113">'C</span><span class="sxs-lookup"><span data-stu-id="156d7-113">'T</span></span>

<span data-ttu-id="156d7-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="156d7-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="156d7-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="156d7-115">See Also</span></span>

- [<span data-ttu-id="156d7-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="156d7-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)