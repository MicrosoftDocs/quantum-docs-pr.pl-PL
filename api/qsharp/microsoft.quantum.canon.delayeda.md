---
uid: Microsoft.Quantum.Canon.DelayedA
title: Funkcja opóźniona
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayedA
qsharp.summary: Returns an operation that applies given operation with given argument.
ms.openlocfilehash: 33ff4dab36a6c6e17b9496a623f70b814c9f2fed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207075"
---
# <a name="delayeda-function"></a><span data-ttu-id="34557-102">Funkcja opóźniona</span><span class="sxs-lookup"><span data-stu-id="34557-102">DelayedA function</span></span>

<span data-ttu-id="34557-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="34557-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="34557-104">Pakiet: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="34557-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="34557-105">Zwraca operację, która stosuje daną operację z danym argumentem.</span><span class="sxs-lookup"><span data-stu-id="34557-105">Returns an operation that applies given operation with given argument.</span></span>

```qsharp
function DelayedA<'T> (op : ('T => Unit is Adj), arg : 'T) : (Unit => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="34557-106">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="34557-106">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="34557-107">op: t = [jednostka](xref:microsoft.quantum.lang-ref.unit) > jest korektą</span><span class="sxs-lookup"><span data-stu-id="34557-107">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="34557-108">Operacja, która ma zostać zastosowana w wyniku zastosowania wartości zwracanej</span><span class="sxs-lookup"><span data-stu-id="34557-108">An operation to be applied as a result of applying return value</span></span>


### <a name="arg--t"></a><span data-ttu-id="34557-109">ARG: 'T</span><span class="sxs-lookup"><span data-stu-id="34557-109">arg : 'T</span></span>

<span data-ttu-id="34557-110">Dane wejściowe, do których `op` zostanie zastosowana operacja.</span><span class="sxs-lookup"><span data-stu-id="34557-110">The input to which the operation `op` is applied.</span></span>



## <a name="output--unit--unit--is-adj"></a><span data-ttu-id="34557-111">Wynik: [Unit](xref:microsoft.quantum.lang-ref.unit) => [Jednostka](xref:microsoft.quantum.lang-ref.unit) jednostki jest korektą</span><span class="sxs-lookup"><span data-stu-id="34557-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="34557-112">Nowa operacja stosowana `op` z danymi wejściowymi `arg`</span><span class="sxs-lookup"><span data-stu-id="34557-112">A new operation which applies `op` with input `arg`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="34557-113">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="34557-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="34557-114">'C</span><span class="sxs-lookup"><span data-stu-id="34557-114">'T</span></span>

<span data-ttu-id="34557-115">Typ wejściowy operacji, która ma zostać opóźniona.</span><span class="sxs-lookup"><span data-stu-id="34557-115">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="34557-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="34557-116">See Also</span></span>

- [<span data-ttu-id="34557-117">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="34557-117">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)
- [<span data-ttu-id="34557-118">Microsoft. Quantum. Canon. Delay</span><span class="sxs-lookup"><span data-stu-id="34557-118">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)