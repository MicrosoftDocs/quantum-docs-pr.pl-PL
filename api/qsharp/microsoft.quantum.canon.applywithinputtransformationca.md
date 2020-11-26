---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA, operacja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207789"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="b1c0b-102">ApplyWithInputTransformationCA, operacja</span><span class="sxs-lookup"><span data-stu-id="b1c0b-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="b1c0b-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1c0b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1c0b-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1c0b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1c0b-105">W przypadku operacji, która akceptuje pewne dane wejściowe, funkcja zwracająca dane wyjściowe zgodne z tą operacją oraz dane wejściowe do tej funkcji, stosuje operację przy użyciu funkcji, aby przekształcić dane wejściowe na formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b1c0b-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="b1c0b-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="b1c0b-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="b1c0b-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="b1c0b-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="b1c0b-109">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="b1c0b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b1c0b-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="b1c0b-111">dane wejściowe: ' U</span><span class="sxs-lookup"><span data-stu-id="b1c0b-111">input : 'U</span></span>

<span data-ttu-id="b1c0b-112">Wejście do funkcji.</span><span class="sxs-lookup"><span data-stu-id="b1c0b-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1c0b-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1c0b-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1c0b-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="b1c0b-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1c0b-115">'C</span><span class="sxs-lookup"><span data-stu-id="b1c0b-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="b1c0b-116">' U</span><span class="sxs-lookup"><span data-stu-id="b1c0b-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="b1c0b-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b1c0b-117">See Also</span></span>

- [<span data-ttu-id="b1c0b-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="b1c0b-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="b1c0b-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="b1c0b-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="b1c0b-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="b1c0b-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="b1c0b-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="b1c0b-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)