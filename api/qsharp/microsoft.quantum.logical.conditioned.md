---
uid: Microsoft.Quantum.Logical.Conditioned
title: Funkcja warunkowa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720789"
---
# <a name="conditioned-function"></a><span data-ttu-id="48737-102">Funkcja warunkowa</span><span class="sxs-lookup"><span data-stu-id="48737-102">Conditioned function</span></span>

<span data-ttu-id="48737-103">Przestrzeń nazw: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="48737-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="48737-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48737-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48737-105">Zwraca jedną z dwóch wartości, w zależności od wartości warunku logicznego.</span><span class="sxs-lookup"><span data-stu-id="48737-105">Returns one of two values, depending on the value of a Boolean condition.</span></span>

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a><span data-ttu-id="48737-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="48737-106">Input</span></span>

### <a name="condition--bool"></a><span data-ttu-id="48737-107">warunek: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="48737-107">condition : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="48737-108">Warunek służący do kontrolowania, które dane wejściowe są zwracane.</span><span class="sxs-lookup"><span data-stu-id="48737-108">A condition used to control which input is returned.</span></span>


### <a name="iftrue--t"></a><span data-ttu-id="48737-109">ifTrue: 'T</span><span class="sxs-lookup"><span data-stu-id="48737-109">ifTrue : 'T</span></span>

<span data-ttu-id="48737-110">Wartość, która ma zostać zwrócona, gdy `condition` jest `true` .</span><span class="sxs-lookup"><span data-stu-id="48737-110">The value to be returned when `condition` is `true`.</span></span>


### <a name="iffalse--t"></a><span data-ttu-id="48737-111">ifFalse: 'T</span><span class="sxs-lookup"><span data-stu-id="48737-111">ifFalse : 'T</span></span>

<span data-ttu-id="48737-112">Wartość, która ma zostać zwrócona, gdy `condition` jest `false` .</span><span class="sxs-lookup"><span data-stu-id="48737-112">The value to be returned when `condition` is `false`.</span></span>



## <a name="output--t"></a><span data-ttu-id="48737-113">Dane wyjściowe: 'T</span><span class="sxs-lookup"><span data-stu-id="48737-113">Output : 'T</span></span>

<span data-ttu-id="48737-114">`ifTrue` Jeśli `condition` jest `true` , i `ifFalse` w inny sposób.</span><span class="sxs-lookup"><span data-stu-id="48737-114">`ifTrue` if `condition` is `true`, and `ifFalse` otherwise.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="48737-115">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="48737-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="48737-116">'C</span><span class="sxs-lookup"><span data-stu-id="48737-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="48737-117">Uwagi</span><span class="sxs-lookup"><span data-stu-id="48737-117">Remarks</span></span>

<span data-ttu-id="48737-118">W przeciwieństwie do `?|` operatora, ta funkcja nie jest krótka obwód, tak że oba dane wejściowe są w pełni oceniane.</span><span class="sxs-lookup"><span data-stu-id="48737-118">Unlike the `?|` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="48737-119">W przypadku zachowania do krótkiego obwodu następujące elementy są równoważne:</span><span class="sxs-lookup"><span data-stu-id="48737-119">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```