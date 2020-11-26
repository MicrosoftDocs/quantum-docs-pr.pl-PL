---
uid: Microsoft.Quantum.Canon.Delay
title: Opóźnienie operacji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 4f45527faa49f79fccff3892e928fed09f9f0bc8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216510"
---
# <a name="delay-operation"></a><span data-ttu-id="93d89-102">Opóźnienie operacji</span><span class="sxs-lookup"><span data-stu-id="93d89-102">Delay operation</span></span>

<span data-ttu-id="93d89-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="93d89-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="93d89-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="93d89-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="93d89-105">Stosuje daną operację z opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="93d89-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="93d89-106">Opis</span><span class="sxs-lookup"><span data-stu-id="93d89-106">Description</span></span>

<span data-ttu-id="93d89-107">Mając daną operację i dane wejściowe dla tej operacji, stosuje operację po udostępnieniu dodatkowych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="93d89-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="93d89-108">W szczególności wyrażenie `Delay(op, arg, _)` jest operacją, która stosuje się `op` do `arg` momentu wywołania.</span><span class="sxs-lookup"><span data-stu-id="93d89-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="93d89-109">Wyrażenie `Delay(op,arg,_)` umożliwia opóźnienie aplikacji `op` .</span><span class="sxs-lookup"><span data-stu-id="93d89-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="93d89-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="93d89-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="93d89-111">op: 'T => ' U</span><span class="sxs-lookup"><span data-stu-id="93d89-111">op : 'T => 'U</span></span> 

<span data-ttu-id="93d89-112">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="93d89-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="93d89-113">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="93d89-113">arg : 'T</span></span>

<span data-ttu-id="93d89-114">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="93d89-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="93d89-115">AUX: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="93d89-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="93d89-116">Argument używany do opóźniania stosowania operacji przy użyciu częściowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="93d89-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="93d89-117">Wynik: ' U</span><span class="sxs-lookup"><span data-stu-id="93d89-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="93d89-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="93d89-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93d89-119">'C</span><span class="sxs-lookup"><span data-stu-id="93d89-119">'T</span></span>

<span data-ttu-id="93d89-120">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="93d89-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="93d89-121">' U</span><span class="sxs-lookup"><span data-stu-id="93d89-121">'U</span></span>

<span data-ttu-id="93d89-122">Zwracany typ operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="93d89-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="93d89-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="93d89-123">See Also</span></span>

- [<span data-ttu-id="93d89-124">Microsoft. Quantum. Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="93d89-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="93d89-125">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="93d89-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="93d89-126">Microsoft. Quantum. Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="93d89-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="93d89-127">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="93d89-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)