---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716669"
---
# <a name="boundc-function"></a><span data-ttu-id="aa32a-102">BoundC, funkcja</span><span class="sxs-lookup"><span data-stu-id="aa32a-102">BoundC function</span></span>

<span data-ttu-id="aa32a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aa32a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aa32a-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="aa32a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="aa32a-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="aa32a-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="aa32a-106">Modyfikator `C` wskazuje, że wszystkie operacje w tablicy są kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="aa32a-106">The modifier `C` indicates that all operations in the array are controllable.</span></span>

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="aa32a-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aa32a-107">Input</span></span>

### <a name="operations--t--unit-ctl"></a><span data-ttu-id="aa32a-108">operacje: 'T =>a lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="aa32a-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl[]</span></span>

<span data-ttu-id="aa32a-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="aa32a-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="aa32a-110">Dane wyjściowe: 'T => [jednostki](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="aa32a-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="aa32a-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="aa32a-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aa32a-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="aa32a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa32a-113">'C</span><span class="sxs-lookup"><span data-stu-id="aa32a-113">'T</span></span>

<span data-ttu-id="aa32a-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="aa32a-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa32a-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aa32a-115">See Also</span></span>

- [<span data-ttu-id="aa32a-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="aa32a-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)