---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 9f564fee38fb22283da4807f829ddc5ec156bf3d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852051"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="0477a-102">TransformedOperation, funkcja</span><span class="sxs-lookup"><span data-stu-id="0477a-102">TransformedOperation function</span></span>

<span data-ttu-id="0477a-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0477a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0477a-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0477a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0477a-105">Dana funkcja i operacja zwracają nową operację, której dane wejściowe są przekształcane przez daną funkcję.</span><span class="sxs-lookup"><span data-stu-id="0477a-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="0477a-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="0477a-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="0477a-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="0477a-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="0477a-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="0477a-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="0477a-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0477a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0477a-110">Operacja, która ma zostać przekształcona.</span><span class="sxs-lookup"><span data-stu-id="0477a-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="0477a-111">Wynik: "U = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="0477a-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0477a-112">Nowa operacja tbat wywołania `fn` z danymi wejściowymi, a następnie przekazuje wynikowe dane wyjściowe do `op` .</span><span class="sxs-lookup"><span data-stu-id="0477a-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0477a-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="0477a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0477a-114">'C</span><span class="sxs-lookup"><span data-stu-id="0477a-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="0477a-115">' U</span><span class="sxs-lookup"><span data-stu-id="0477a-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="0477a-116">Przykład</span><span class="sxs-lookup"><span data-stu-id="0477a-116">Example</span></span>

<span data-ttu-id="0477a-117">Poniższe wywołanie używa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" do przekształcenia operacji przeznaczonej do wprowadzania @"Microsoft.Quantum.Arithmetic.BigEndian" danych wejściowych do operacji akceptującej dane wejściowe typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="0477a-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="0477a-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0477a-118">See Also</span></span>

- [<span data-ttu-id="0477a-119">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="0477a-119">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="0477a-120">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="0477a-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="0477a-121">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="0477a-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="0477a-122">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="0477a-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="0477a-123">Microsoft. Quantum. Canon. złożona</span><span class="sxs-lookup"><span data-stu-id="0477a-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)