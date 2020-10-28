---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow, funkcja
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 5cf9017175f44a8a0b8f865624a6c312d25aded1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715773"
---
# <a name="operationpow-function"></a><span data-ttu-id="3074f-102">OperationPow, funkcja</span><span class="sxs-lookup"><span data-stu-id="3074f-102">OperationPow function</span></span>

<span data-ttu-id="3074f-103">Przestrzeń nazw: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3074f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3074f-104">Package [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3074f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3074f-105">Wywołuje operację do potęgi.</span><span class="sxs-lookup"><span data-stu-id="3074f-105">Raises an operation to a power.</span></span>

<span data-ttu-id="3074f-106">Oznacza to, że w wyniku operacji reprezentującej bramę $U $, zwraca nową operację $U ^ m $ dla $m potęgi $.</span><span class="sxs-lookup"><span data-stu-id="3074f-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="3074f-107">Dane wejściowe</span><span class="sxs-lookup"><span data-stu-id="3074f-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="3074f-108">op: 'T = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3074f-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3074f-109">Operacja $U $ reprezentująca bramę do powtórzenia.</span><span class="sxs-lookup"><span data-stu-id="3074f-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="3074f-110">potęga: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3074f-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3074f-111">Liczba powtórzeń $U $.</span><span class="sxs-lookup"><span data-stu-id="3074f-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="3074f-112">Dane wyjściowe: t = [jednostka](xref:microsoft.quantum.lang-ref.unit)></span><span class="sxs-lookup"><span data-stu-id="3074f-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3074f-113">Nowa operacja reprezentująca $U ^ m $, gdzie $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="3074f-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3074f-114">Parametry typu</span><span class="sxs-lookup"><span data-stu-id="3074f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3074f-115">'C</span><span class="sxs-lookup"><span data-stu-id="3074f-115">'T</span></span>

<span data-ttu-id="3074f-116">Typ operacji, która ma być włączona.</span><span class="sxs-lookup"><span data-stu-id="3074f-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="3074f-117">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3074f-117">See Also</span></span>

- [<span data-ttu-id="3074f-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="3074f-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="3074f-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="3074f-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="3074f-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="3074f-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)