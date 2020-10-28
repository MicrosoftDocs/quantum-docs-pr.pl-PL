---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: b6867a076b654337f6127657189a8453c9973cc2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715325"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="5cc01-102">TransformedOperationC, funkcja</span><span class="sxs-lookup"><span data-stu-id="5cc01-102">TransformedOperationC function</span></span>

<span data-ttu-id="5cc01-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5cc01-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5cc01-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5cc01-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5cc01-105">Dana funkcja i operacja zwracają nową operację, której dane wejściowe są przekształcane przez daną funkcję.</span><span class="sxs-lookup"><span data-stu-id="5cc01-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="5cc01-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5cc01-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="5cc01-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="5cc01-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="5cc01-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="5cc01-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="5cc01-109">op: 'T => — lista CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5cc01-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5cc01-110">Operacja, która ma zostać przekształcona.</span><span class="sxs-lookup"><span data-stu-id="5cc01-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-ctl"></a><span data-ttu-id="5cc01-111">Dane wyjściowe: "U => CTL [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5cc01-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="5cc01-112">Nowa operacja tbat wywołania `fn` z danymi wejściowymi, a następnie przekazuje wynikowe dane wyjściowe do `op` .</span><span class="sxs-lookup"><span data-stu-id="5cc01-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5cc01-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5cc01-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5cc01-114">'C</span><span class="sxs-lookup"><span data-stu-id="5cc01-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="5cc01-115">' U</span><span class="sxs-lookup"><span data-stu-id="5cc01-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="5cc01-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5cc01-116">See Also</span></span>

- [<span data-ttu-id="5cc01-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="5cc01-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="5cc01-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="5cc01-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="5cc01-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="5cc01-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="5cc01-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="5cc01-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="5cc01-121">Microsoft. Quantum. Canon. złożona</span><span class="sxs-lookup"><span data-stu-id="5cc01-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)