---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation, operacja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: d4589acbe9f9dc6c6ab665582ed663dbc193edbb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850373"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="20559-102">ApplyWithInputTransformation, operacja</span><span class="sxs-lookup"><span data-stu-id="20559-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="20559-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="20559-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="20559-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="20559-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="20559-105">W przypadku operacji, która akceptuje pewne dane wejściowe, funkcja zwracająca dane wyjściowe zgodne z tą operacją oraz dane wejściowe do tej funkcji, stosuje operację przy użyciu funkcji, aby przekształcić dane wejściowe na formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="20559-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="20559-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="20559-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="20559-107">fn: "U-> t</span><span class="sxs-lookup"><span data-stu-id="20559-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="20559-108">Funkcja, która przekształca dane wejściowe w formularz oczekiwany przez operację.</span><span class="sxs-lookup"><span data-stu-id="20559-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="20559-109">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="20559-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="20559-110">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="20559-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="20559-111">dane wejściowe: ' U</span><span class="sxs-lookup"><span data-stu-id="20559-111">input : 'U</span></span>

<span data-ttu-id="20559-112">Wejście do funkcji.</span><span class="sxs-lookup"><span data-stu-id="20559-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20559-113">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20559-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="20559-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="20559-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="20559-115">'C</span><span class="sxs-lookup"><span data-stu-id="20559-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="20559-116">' U</span><span class="sxs-lookup"><span data-stu-id="20559-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="20559-117">Przykład</span><span class="sxs-lookup"><span data-stu-id="20559-117">Example</span></span>

<span data-ttu-id="20559-118">Następujące wywołanie używa @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" do zastosowania operacji przeznaczonej do @"Microsoft.Quantum.Arithmetic.BigEndian" wejścia na dane wejściowe typu @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="20559-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="20559-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="20559-119">See Also</span></span>

- [<span data-ttu-id="20559-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="20559-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="20559-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="20559-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="20559-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="20559-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="20559-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="20559-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)