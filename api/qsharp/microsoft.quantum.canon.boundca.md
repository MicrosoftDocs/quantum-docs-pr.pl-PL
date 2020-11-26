---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 774a6f57566dce75b98290a7e81540b28afea1af
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216885"
---
# <a name="boundca-function"></a><span data-ttu-id="749ee-102">BoundCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="749ee-102">BoundCA function</span></span>

<span data-ttu-id="749ee-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="749ee-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="749ee-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="749ee-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="749ee-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="749ee-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="749ee-106">Modyfikator `CA` wskazuje, że wszystkie operacje w tablicy są sąsiadujące i kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="749ee-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="749ee-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="749ee-107">Input</span></span>

### <a name="operations--t--unit--is-adj--ctl"></a><span data-ttu-id="749ee-108">operacje: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL []</span><span class="sxs-lookup"><span data-stu-id="749ee-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="749ee-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="749ee-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit--is-adj--ctl"></a><span data-ttu-id="749ee-110">Wynik: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą i listą CTL</span><span class="sxs-lookup"><span data-stu-id="749ee-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="749ee-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="749ee-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="749ee-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="749ee-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="749ee-113">'C</span><span class="sxs-lookup"><span data-stu-id="749ee-113">'T</span></span>

<span data-ttu-id="749ee-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="749ee-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="749ee-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="749ee-115">See Also</span></span>

- [<span data-ttu-id="749ee-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="749ee-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)