---
uid: Microsoft.Quantum.Canon.DelayedA
title: Funkcja opóźniona
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 11c11cdd75d80d6324666ef56930f7a522121826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716249"
---
# <a name="delayeda-function"></a><span data-ttu-id="f7774-102">Funkcja opóźniona</span><span class="sxs-lookup"><span data-stu-id="f7774-102">DelayedA function</span></span>

<span data-ttu-id="f7774-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f7774-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f7774-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f7774-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f7774-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="f7774-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="f7774-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="f7774-106">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="f7774-107">op: 'T => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f7774-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f7774-108">Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej</span><span class="sxs-lookup"><span data-stu-id="f7774-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="f7774-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="f7774-109">arg : 'T</span></span>

<span data-ttu-id="f7774-110">Dane wejściowe, do których `op` zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="f7774-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit-adj"></a><span data-ttu-id="f7774-111">Wynik: [Unit](xref:microsoft.quantum.lang-ref.unit) => korekta [jednostki](xref:microsoft.quantum.lang-ref.unit) jednostki</span><span class="sxs-lookup"><span data-stu-id="f7774-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="f7774-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="f7774-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f7774-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="f7774-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f7774-114">'C</span><span class="sxs-lookup"><span data-stu-id="f7774-114">'T</span></span>

<span data-ttu-id="f7774-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="f7774-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="f7774-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f7774-116">See Also</span></span>

- [<span data-ttu-id="f7774-117">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="f7774-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="f7774-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="f7774-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)