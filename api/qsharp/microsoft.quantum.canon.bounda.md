---
uid: Microsoft.Quantum.Canon.BoundA
title: Bound — funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3132bf198e98dd1a2b433f36b000060e7e721865
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216952"
---
# <a name="bounda-function"></a><span data-ttu-id="f6ec3-102">Bound — funkcja</span><span class="sxs-lookup"><span data-stu-id="f6ec3-102">BoundA function</span></span>

<span data-ttu-id="f6ec3-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f6ec3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f6ec3-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f6ec3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f6ec3-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="f6ec3-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="f6ec3-106">Modyfikator `A` wskazuje, że wszystkie operacje w tablicy są sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="f6ec3-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="f6ec3-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f6ec3-107">Input</span></span>

### <a name="operations--t--unit--is-adj"></a><span data-ttu-id="f6ec3-108">operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą []</span><span class="sxs-lookup"><span data-stu-id="f6ec3-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj[]</span></span>

<span data-ttu-id="f6ec3-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="f6ec3-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="f6ec3-110">Wartość wyjściowa: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="f6ec3-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f6ec3-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="f6ec3-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f6ec3-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f6ec3-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f6ec3-113">'C</span><span class="sxs-lookup"><span data-stu-id="f6ec3-113">'T</span></span>

<span data-ttu-id="f6ec3-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="f6ec3-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6ec3-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f6ec3-115">See Also</span></span>

- [<span data-ttu-id="f6ec3-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="f6ec3-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)