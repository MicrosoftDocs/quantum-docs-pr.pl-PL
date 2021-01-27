---
uid: Microsoft.Quantum.Canon.DelayedCA
title: DelayedCA, funkcja
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedCA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: c44e3448c471f2a20f995d4546ee54f3affb726e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840548"
---
# <a name="delayedca-function"></a><span data-ttu-id="07bf1-102">DelayedCA, funkcja</span><span class="sxs-lookup"><span data-stu-id="07bf1-102">DelayedCA function</span></span>

<span data-ttu-id="07bf1-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="07bf1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="07bf1-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="07bf1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="07bf1-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="07bf1-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedCA<'T> (op : ('T => Unit is Ctl + Adj), arg : 'T) : (Unit => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="07bf1-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="07bf1-106">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="07bf1-107">op: 'R => [Unit](xref:microsoft.quantum.lang-ref.unit)  to przymiotnik + CTL</span><span class="sxs-lookup"><span data-stu-id="07bf1-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="07bf1-108">Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej</span><span class="sxs-lookup"><span data-stu-id="07bf1-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="07bf1-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="07bf1-109">arg : 'T</span></span>

<span data-ttu-id="07bf1-110">Dane wejściowe, do których `op` zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="07bf1-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj--ctl"></a><span data-ttu-id="07bf1-111">Wynik: [Jednostka jednostkowa](xref:microsoft.quantum.lang-ref.unit) => [](xref:microsoft.quantum.lang-ref.unit) to korekta i CTL</span><span class="sxs-lookup"><span data-stu-id="07bf1-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="07bf1-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="07bf1-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="07bf1-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="07bf1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="07bf1-114">'C</span><span class="sxs-lookup"><span data-stu-id="07bf1-114">'T</span></span>

<span data-ttu-id="07bf1-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="07bf1-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="07bf1-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="07bf1-116">See Also</span></span>

- [<span data-ttu-id="07bf1-117">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="07bf1-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="07bf1-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="07bf1-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)