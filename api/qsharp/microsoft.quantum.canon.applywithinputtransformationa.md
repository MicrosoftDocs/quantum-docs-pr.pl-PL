---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207891"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="aebcf-102">ApplyWithInputTransformationA, operacja</span><span class="sxs-lookup"><span data-stu-id="aebcf-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="aebcf-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="aebcf-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="aebcf-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aebcf-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aebcf-105">W przypadku operacji, która akceptuje pewne dane wejściowe, funkcja zwracająca dane wyjściowe zgodne z tą operacją oraz dane wejściowe do tej funkcji, stosuje operację przy użyciu funkcji, aby przekształcić dane wejściowe na formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="aebcf-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="aebcf-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="aebcf-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="aebcf-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="aebcf-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="aebcf-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="aebcf-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="aebcf-109">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="aebcf-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="aebcf-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="aebcf-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="aebcf-111">dane wejściowe: ' U</span><span class="sxs-lookup"><span data-stu-id="aebcf-111">input : 'U</span></span>

<span data-ttu-id="aebcf-112">Wejście do funkcji.</span><span class="sxs-lookup"><span data-stu-id="aebcf-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="aebcf-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="aebcf-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="aebcf-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="aebcf-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aebcf-115">'C</span><span class="sxs-lookup"><span data-stu-id="aebcf-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="aebcf-116">' U</span><span class="sxs-lookup"><span data-stu-id="aebcf-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="aebcf-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="aebcf-117">See Also</span></span>

- [<span data-ttu-id="aebcf-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="aebcf-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="aebcf-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="aebcf-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="aebcf-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="aebcf-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="aebcf-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="aebcf-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)