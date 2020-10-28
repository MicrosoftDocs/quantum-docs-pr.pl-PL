---
uid: Microsoft.Quantum.Canon.BoundA
title: Bound — funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716688"
---
# <a name="bounda-function"></a><span data-ttu-id="4e764-102">Bound — funkcja</span><span class="sxs-lookup"><span data-stu-id="4e764-102">BoundA function</span></span>

<span data-ttu-id="4e764-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4e764-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4e764-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4e764-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4e764-105">Dana tablica operacji działających na pojedynczym wejściu tworzy nową operację, która wykonuje każdą daną operację w sekwencji.</span><span class="sxs-lookup"><span data-stu-id="4e764-105">Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.</span></span>
<span data-ttu-id="4e764-106">Modyfikator `A` wskazuje, że wszystkie operacje w tablicy są sąsiadujące.</span><span class="sxs-lookup"><span data-stu-id="4e764-106">The modifier `A` indicates that all operations in the array are adjointable.</span></span>

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="4e764-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4e764-107">Input</span></span>

### <a name="operations--t--unit-adj"></a><span data-ttu-id="4e764-108">operacje: t => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="4e764-108">operations : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj[]</span></span>

<span data-ttu-id="4e764-109">Sekwencja operacji do wykonania na danym wejściu.</span><span class="sxs-lookup"><span data-stu-id="4e764-109">A sequence of operations to be performed on a given input.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="4e764-110">Wynik: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4e764-110">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="4e764-111">Nowa operacja wykonująca każdą daną operację w sekwencji na jej wejściu.</span><span class="sxs-lookup"><span data-stu-id="4e764-111">A new operation that performs each given operation in sequence on its input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4e764-112">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4e764-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4e764-113">'C</span><span class="sxs-lookup"><span data-stu-id="4e764-113">'T</span></span>

<span data-ttu-id="4e764-114">Obiekt docelowy, na którym każda z operacji w tablicy działa.</span><span class="sxs-lookup"><span data-stu-id="4e764-114">The target on which each of the operations in the array act.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e764-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4e764-115">See Also</span></span>

- [<span data-ttu-id="4e764-116">Microsoft. Quantum. Canon. Bound</span><span class="sxs-lookup"><span data-stu-id="4e764-116">Microsoft.Quantum.Canon.Bound</span></span>](xref:Microsoft.Quantum.Canon.Bound)