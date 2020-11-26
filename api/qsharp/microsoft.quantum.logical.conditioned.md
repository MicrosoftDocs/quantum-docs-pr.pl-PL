---
uid: Microsoft.Quantum.Logical.Conditioned
title: Funkcja warunkowa
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: c0f55d4db95ad1f0d2b7f291cbc6ba8ae704cb81
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198490"
---
# <a name="conditioned-function"></a><span data-ttu-id="94c52-102">Funkcja warunkowa</span><span class="sxs-lookup"><span data-stu-id="94c52-102">Conditioned function</span></span>

<span data-ttu-id="94c52-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="94c52-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="94c52-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="94c52-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="94c52-105">Zwraca jedną z dwóch wartości, w zależności od wartości warunku logicznego.</span><span class="sxs-lookup"><span data-stu-id="94c52-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="94c52-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="94c52-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="94c52-107">warunek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="94c52-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="94c52-108">Warunek służący do kontrolowania, które dane wejściowe są zwracane.</span><span class="sxs-lookup"><span data-stu-id="94c52-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="94c52-109">ifTrue: 'T</span><span class="sxs-lookup"><span data-stu-id="94c52-109">ifTrue : 'T</span></span>

<span data-ttu-id="94c52-110">Wartość, która ma zostać zwrócona, gdy `condition` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="94c52-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="94c52-111">ifFalse: 'T</span><span class="sxs-lookup"><span data-stu-id="94c52-111">ifFalse : 'T</span></span>

<span data-ttu-id="94c52-112">Wartość, która ma zostać zwrócona, gdy `condition` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="94c52-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="94c52-113">Dane wyjściowe: 'T</span><span class="sxs-lookup"><span data-stu-id="94c52-113">Output : 'T</span></span>

<span data-ttu-id="94c52-114">`ifTrue` Jeśli `condition` jest `true` , i `ifFalse` w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="94c52-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="94c52-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="94c52-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="94c52-116">'C</span><span class="sxs-lookup"><span data-stu-id="94c52-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="94c52-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="94c52-117">Remarks</span></span>

<span data-ttu-id="94c52-118">W przeciwieństwie do `?|` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.</span><span class="sxs-lookup"><span data-stu-id="94c52-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="94c52-119">W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="94c52-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```