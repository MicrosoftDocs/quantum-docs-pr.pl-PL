---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA, operacja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716851"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="766a9-102">ApplyWithInputTransformationA, operacja</span><span class="sxs-lookup"><span data-stu-id="766a9-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="766a9-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="766a9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="766a9-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="766a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="766a9-105">W przypadku operacji, która akceptuje pewne dane wejściowe, funkcja zwracająca dane wyjściowe zgodne z tą operacją oraz dane wejściowe do tej funkcji, stosuje operację przy użyciu funkcji, aby przekształcić dane wejściowe na formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="766a9-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="766a9-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="766a9-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="766a9-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="766a9-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="766a9-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="766a9-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="766a9-109">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="766a9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="766a9-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="766a9-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="766a9-111">dane wejściowe: ' U</span><span class="sxs-lookup"><span data-stu-id="766a9-111">input : 'U</span></span>

<span data-ttu-id="766a9-112">Wejście do funkcji.</span><span class="sxs-lookup"><span data-stu-id="766a9-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="766a9-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="766a9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="766a9-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="766a9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="766a9-115">'C</span><span class="sxs-lookup"><span data-stu-id="766a9-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="766a9-116">' U</span><span class="sxs-lookup"><span data-stu-id="766a9-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="766a9-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="766a9-117">See Also</span></span>

- [<span data-ttu-id="766a9-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="766a9-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="766a9-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="766a9-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="766a9-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="766a9-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="766a9-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="766a9-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)