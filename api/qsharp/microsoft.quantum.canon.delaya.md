---
uid: Microsoft.Quantum.Canon.DelayA
title: Opóźnienie operacji
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7c3325fd98a85c7e9123f383cbdc0a68627222c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207143"
---
# <a name="delaya-operation"></a><span data-ttu-id="64837-102">Opóźnienie operacji</span><span class="sxs-lookup"><span data-stu-id="64837-102">DelayA operation</span></span>

<span data-ttu-id="64837-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64837-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64837-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="64837-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="64837-105">Stosuje daną operację z opóźnieniem.</span><span class="sxs-lookup"><span data-stu-id="64837-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="64837-106">Opis</span><span class="sxs-lookup"><span data-stu-id="64837-106">Description</span></span>

<span data-ttu-id="64837-107">Mając daną operację i dane wejściowe dla tej operacji, stosuje operację po udostępnieniu dodatkowych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="64837-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="64837-108">W szczególności wyrażenie `Delay(op, arg, _)` jest operacją, która stosuje się `op` do `arg` momentu wywołania.</span><span class="sxs-lookup"><span data-stu-id="64837-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="64837-109">Wyrażenie `Delay(op,arg,_)` umożliwia opóźnienie aplikacji `op` .</span><span class="sxs-lookup"><span data-stu-id="64837-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="64837-110">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="64837-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="64837-111">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="64837-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="64837-112">Operacja, która ma zostać zastosowana.</span><span class="sxs-lookup"><span data-stu-id="64837-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="64837-113">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="64837-113">arg : 'T</span></span>

<span data-ttu-id="64837-114">Dane wejściowe, do których zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="64837-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="64837-115">AUX: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64837-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="64837-116">Argument używany do opóźniania stosowania operacji przy użyciu częściowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="64837-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64837-117">Dane wyjściowe: [Jednostka](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64837-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="64837-118">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="64837-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64837-119">'C</span><span class="sxs-lookup"><span data-stu-id="64837-119">'T</span></span>

<span data-ttu-id="64837-120">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="64837-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="64837-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="64837-121">See Also</span></span>

- [<span data-ttu-id="64837-122">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="64837-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="64837-123">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="64837-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)