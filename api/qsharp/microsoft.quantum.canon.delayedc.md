---
uid: Microsoft.Quantum.Canon.DelayedC
title: DelayedC, funkcja
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedC
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: d8036397559b1587b806f701d89e892eea2da8f9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207019"
---
# <a name="delayedc-function"></a><span data-ttu-id="4c2c1-102">DelayedC, funkcja</span><span class="sxs-lookup"><span data-stu-id="4c2c1-102">DelayedC function</span></span>

<span data-ttu-id="4c2c1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4c2c1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4c2c1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4c2c1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4c2c1-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="4c2c1-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedC<'T> (op : ('T => Unit is Ctl), arg : 'T) : (Unit => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="4c2c1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="4c2c1-106">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="4c2c1-107">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="4c2c1-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4c2c1-108">Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej</span><span class="sxs-lookup"><span data-stu-id="4c2c1-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="4c2c1-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="4c2c1-109">arg : 'T</span></span>

<span data-ttu-id="4c2c1-110">Dane wejściowe, do których `op` zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="4c2c1-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-ctl"></a><span data-ttu-id="4c2c1-111">Wynik: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) jednostki jest listą CTL</span><span class="sxs-lookup"><span data-stu-id="4c2c1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="4c2c1-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="4c2c1-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4c2c1-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="4c2c1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4c2c1-114">'C</span><span class="sxs-lookup"><span data-stu-id="4c2c1-114">'T</span></span>

<span data-ttu-id="4c2c1-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="4c2c1-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c2c1-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4c2c1-116">See Also</span></span>

- [<span data-ttu-id="4c2c1-117">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="4c2c1-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="4c2c1-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="4c2c1-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)