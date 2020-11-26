---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3586e9a114a550fb1989186e9c18fe4f344cf060
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217190"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="5e307-102">ApplyWithInputTransformation, operacja</span><span class="sxs-lookup"><span data-stu-id="5e307-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="5e307-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5e307-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5e307-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e307-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e307-105">W przypadku operacji, która akceptuje pewne dane wejściowe, funkcja zwracająca dane wyjściowe zgodne z tą operacją oraz dane wejściowe do tej funkcji, stosuje operację przy użyciu funkcji, aby przekształcić dane wejściowe na formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="5e307-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="5e307-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="5e307-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="5e307-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="5e307-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="5e307-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="5e307-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="5e307-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="5e307-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="5e307-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="5e307-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="5e307-111">dane wejściowe: ' U</span><span class="sxs-lookup"><span data-stu-id="5e307-111">input : 'U</span></span>

<span data-ttu-id="5e307-112">Wejście do funkcji.</span><span class="sxs-lookup"><span data-stu-id="5e307-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e307-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e307-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5e307-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="5e307-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5e307-115">'C</span><span class="sxs-lookup"><span data-stu-id="5e307-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="5e307-116">' U</span><span class="sxs-lookup"><span data-stu-id="5e307-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="5e307-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="5e307-117">See Also</span></span>

- [<span data-ttu-id="5e307-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="5e307-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="5e307-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="5e307-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="5e307-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="5e307-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="5e307-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="5e307-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)