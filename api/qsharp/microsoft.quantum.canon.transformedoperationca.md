---
uid: Microsoft.Quantum.Canon.TransformedOperationCA
title: TransformedOperationCA, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationCA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 21c9cdfc3b5b266cb3b93e52ee2fa4c655caf795
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715316"
---
# <a name="transformedoperationca-function"></a><span data-ttu-id="75942-102">TransformedOperationCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="75942-102">TransformedOperationCA function</span></span>

<span data-ttu-id="75942-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="75942-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="75942-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75942-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75942-105">Dana funkcja i operacja zwracają nową operację, której dane wejściowe są przekształcane przez daną funkcję.</span><span class="sxs-lookup"><span data-stu-id="75942-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl)) : ('U => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="75942-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="75942-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="75942-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="75942-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="75942-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="75942-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="75942-109">op: 'T => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="75942-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="75942-110">Operacja, która ma zostać przekształcona.</span><span class="sxs-lookup"><span data-stu-id="75942-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-adj--ctl"></a><span data-ttu-id="75942-111">Wynik: ' U => skorygowania [jednostki](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="75942-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="75942-112">Nowa operacja tbat wywołania `fn` z danymi wejściowymi, a następnie przekazuje wynikowe dane wyjściowe do `op` .</span><span class="sxs-lookup"><span data-stu-id="75942-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="75942-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="75942-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="75942-114">'C</span><span class="sxs-lookup"><span data-stu-id="75942-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="75942-115">' U</span><span class="sxs-lookup"><span data-stu-id="75942-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="75942-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="75942-116">See Also</span></span>

- [<span data-ttu-id="75942-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="75942-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="75942-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="75942-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="75942-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="75942-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="75942-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="75942-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="75942-121">Microsoft. Quantum. Canon. złożona</span><span class="sxs-lookup"><span data-stu-id="75942-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)