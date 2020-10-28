---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: d96d33781def10940479ba2eafdcc6711a0c05a5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716632"
---
# <a name="boundca-function"></a><span data-ttu-id="2260f-102">BoundCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="2260f-102">BoundCA function</span></span>

<span data-ttu-id="2260f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2260f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2260f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2260f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2260f-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="2260f-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="2260f-106">Modyfikator `CA` wskazuje, że wszystkie operacje w tablicy są sąsiadujące i kontrolowane.</span><span class="sxs-lookup"><span data-stu-id="2260f-106">The modifier `CA` indicates that all operations in the array are adjointable and controllable.</span></span>

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="2260f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="2260f-107">Input</span></span>

### <a name="operations--t--unit-adj--ctl"></a><span data-ttu-id="2260f-108">operacje: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL []</span><span class="sxs-lookup"><span data-stu-id="2260f-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="2260f-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="2260f-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj--ctl"></a><span data-ttu-id="2260f-110">Wynik: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="2260f-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="2260f-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="2260f-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2260f-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="2260f-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2260f-113">'C</span><span class="sxs-lookup"><span data-stu-id="2260f-113">'T</span></span>

<span data-ttu-id="2260f-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="2260f-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="2260f-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2260f-115">See Also</span></span>

- [<span data-ttu-id="2260f-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="2260f-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)