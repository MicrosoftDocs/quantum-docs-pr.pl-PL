---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: a26cc178f67fd99324355ac230d9e91081b6e238
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204933"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="8f95a-102">TransformedOperation, funkcja</span><span class="sxs-lookup"><span data-stu-id="8f95a-102">TransformedOperation function</span></span>

<span data-ttu-id="8f95a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f95a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f95a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f95a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f95a-105">Dana funkcja i operacja zwracają nową operację, której dane wejściowe są przekształcane przez daną funkcję.</span><span class="sxs-lookup"><span data-stu-id="8f95a-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="8f95a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="8f95a-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="8f95a-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="8f95a-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="8f95a-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="8f95a-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="8f95a-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8f95a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8f95a-110">Operacja, która ma zostać przekształcona.</span><span class="sxs-lookup"><span data-stu-id="8f95a-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="8f95a-111">Wynik: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="8f95a-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8f95a-112">Nowa operacja tbat wywołania `fn` z danymi wejściowymi, a następnie przekazuje wynikowe dane wyjściowe do `op` .</span><span class="sxs-lookup"><span data-stu-id="8f95a-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8f95a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="8f95a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f95a-114">'C</span><span class="sxs-lookup"><span data-stu-id="8f95a-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="8f95a-115">' U</span><span class="sxs-lookup"><span data-stu-id="8f95a-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="8f95a-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8f95a-116">See Also</span></span>

- [<span data-ttu-id="8f95a-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="8f95a-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="8f95a-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="8f95a-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="8f95a-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="8f95a-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="8f95a-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="8f95a-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="8f95a-121">Microsoft. Quantum. Canon. złożona</span><span class="sxs-lookup"><span data-stu-id="8f95a-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)